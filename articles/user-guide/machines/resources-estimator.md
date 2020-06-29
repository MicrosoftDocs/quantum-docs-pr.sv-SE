---
title: Resurs uppskattning för Quantum Development Kit-resurser
description: 'Lär dig mer om resurs uppskattningen som beräknar de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415273"
---
# <a name="the-resources-estimator-target-machine"></a>Mål datorn för resurs uppskattning

När namnet antyder `ResourcesEstimator` beräknar beräkningen de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.
Detta åstadkommer detta genom att köra åtgärden Quantum utan att faktiskt simulera status för en Quantum-dator. av den anledningen kan IT uppskatta resurser för Q #-åtgärder som använder tusentals qubits, om den klassiska delen av koden kan köras på rimlig tid.

## <a name="usage"></a>Användning

`ResourcesEstimator`Är bara en annan typ av måldator, vilket innebär att den kan användas för att köra valfri Q #-åtgärd. 

Som andra mål datorer ska du använda den på ett C#-värdprogram för att skapa en instans och skicka den som den första parametern för åtgärdens `Run` metod:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Som exemplet visar `ResourcesEstimator` tillhandahåller en `ToTSV()` metod för att skapa en tabell med Tabbavgränsade värden (TSV) som kan sparas i en fil eller som skrivs till konsolen för analys. Resultatet av programmet ovan bör se ut ungefär så här:

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> I `ResourcesEstimator` återställs inte beräkningarna vid varje körning, om samma instans används för att köra en annan åtgärd, kommer den att behålla agg regeringar som räknas ovanpå befintliga resultat.
> Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.


## <a name="programmatically-retrieving-the-estimated-data"></a>Hämta beräknade data program mässigt

Förutom en TSV-tabell kan de uppskattade resurserna hämtas via programmering via `ResourcesEstimator` `Data` egenskapen. `Data`tillhandahåller en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerad av mått namnen.

Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` `T` och portar som `CNOT` används av en Q #-åtgärd:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Rapporterade mått

Följande är en lista över mått som beräknas av `ResourcesEstimator` :

* __CNOT__: antalet CNOT (kallas även för de kontrollerade Pauli X-grindarna) som körs.
* __QubitClifford__: antalet enskilda qubit-Clifford och Pauli-portar som körs.
* __Mått__: antalet utförda mätningar.
* __R__: antalet enskilda qubit-rotationer som körs, med undantag för T-, Clifford-och Pauli-portar.
* __T__: antalet t-grindar och deras konjugat, inklusive T-grind, T_x = H. T. H och T_y = hy. T. hy, körs.
* __Djup__: den nedre gränserna för djupet i Quantum-kretsen som körs av åtgärden Q #. Som standard räknas bara T-portar i djupet. mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: den nedre gränsen för maximalt antal allokerade qubits under körningen av Q #-åtgärden. Det kanske inte går att uppnå både __djup__ och __Bredd__ nedre gränser samtidigt.
* __BorrowedWidth__: det maximala antalet qubits som lånas inom Q #-åtgärden.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mätresultatet

<xref:microsoft.quantum.intrinsic.assertprob>från <xref:microsoft.quantum.intrinsic> namn området kan användas för att ge information om den förväntade sannolikheten för en mätning för att köra körningen av Q #-programmet. Följande exempel illustrerar detta:

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

När de `ResourcesEstimator` påträffar `AssertProb` registreras det att mäta `PauliZ` `source` och `q` ska få ett resultat av `Zero` med sannolikhet 0,5. När den körs `M` senare kommer den att hitta de registrerade värdena för resultatet sannolikhet och `M` returnerar `Zero` eller `One` med sannolikhet 0,5.


## <a name="see-also"></a>Se även

`ResourcesEstimator`Är byggd ovanpå dator [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro)från Quantum, som ger en mer omfattande uppsättning mått, möjlighet att rapportera mått för det fullständiga anrops diagrammet och funktioner som [distinkta inmatnings kontroll](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) för att hitta buggar i Q #-program. Mer information finns i dokumentationen för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

