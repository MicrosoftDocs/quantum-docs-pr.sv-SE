---
title: Resurs uppskattning för Quantum Development Kit-resurser | Microsoft Docs
description: Översikt över Microsofts resurs uppskattning för Quantum Development Kit-resurser
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184992"
---
# <a name="the-resourcesestimator-target-machine"></a>Mål datorn för ResourcesEstimator

Som namnet antyder beräknar `ResourcesEstimator` de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.
Detta åstadkommer detta genom att köra åtgärden Quantum utan att faktiskt simulera status för en Quantum-dator. av den anledningen kan IT uppskatta resurser för Q #-åtgärder som använder tusentals qubits.

## <a name="usage"></a>Användning

`ResourcesEstimator` är bara en annan typ av måldator, vilket innebär att den kan användas för att köra en Q #-åtgärd. 

Som andra mål datorer ska du använda den på ett C# värd program för att skapa en instans och skicka den som den första parametern i åtgärdens `Run` metod:

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

I exemplet visar `ResourcesEstimator` en `ToTSV()` metod för att generera en tabell med Tabbavgränsade värden (TSV) som kan sparas i en fil eller som skrivs till konsolen för analys. Resultatet av programmet ovan bör se ut ungefär så här:

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
> `ResourcesEstimator` återställer inte beräkningarna vid varje körning, om samma instans används för att köra en annan åtgärd, så behåller den agg regeringar som räknas ovanpå befintliga resultat.
> Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.


## <a name="programmatically-retrieving-the-estimated-data"></a>Hämta beräknade data program mässigt

Förutom en TSV-tabell kan de beräknade resurserna hämtas via programmering via `ResourcesEstimator``Data` egenskap. `Data` innehåller en `System.DataTable` instans med två kolumner: `Metric` och `Sum`, indexerad av mått namnen.

Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford`, `T` och `CNOT` portar som används av en Q #-åtgärd:

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

Följande är en lista över mått som beräknas av `ResourcesEstimator`:

* __CNOT__: antalet CNOT (kallas även för de kontrollerade Pauli X-grindarna) som körs.
* __QubitClifford__: antalet enskilda qubit-Clifford och Pauli-portar som körs.
* __Mått__: antalet utförda mätningar.
* __R__: antalet enskilda qubit-rotationer som körs, med undantag för T-, Clifford-och Pauli-portar.
* __T__: antalet t-grindar och deras konjugat, inklusive T-grind, T_x = H. T. H och T_y = hy. T. hy, utförs.
* __Djup__: djupet i Quantum-kretsen som körs av åtgärden Q #. Som standard räknas bara T-portar i djupet. mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: det högsta antalet qubits som tilldelas under körningen av Q #-åtgärden.
* __BorrowedWidth__: det maximala antalet qubits som lånas inom Q #-åtgärden.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mått resultat

<xref:microsoft.quantum.primitive.assertprob> från namn området <xref:microsoft.quantum.primitive> kan användas för att ge information om den förväntade sannolikheten för en mätning för att köra körningen av Q #-programmet. Följande exempel illustrerar detta:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

När `ResourcesEstimator` påträffar `AssertProb` registreras att mät `PauliZ` på `source` och `ancilla` bör få ett resultat av `Zero` med sannolikhet 0,5. När den körs `M` senare kommer den att hitta de inspelade värdena för resultatet sannolikhet och `M` returnerar `Zero` eller `One` med sannolikhet 0,5.


## <a name="see-also"></a>Se också

`ResourcesEstimator` bygger på den väntande dator [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro), som ger en mer omfattande uppsättning mått, möjlighet att rapportera mått för det fullständiga anrops diagrammet och funktioner som [distinkta inmatnings kontroll](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) för att hitta buggar i Q #-program. Mer information finns i dokumentationen för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
