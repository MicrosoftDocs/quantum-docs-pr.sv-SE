---
title: Uppskattningar av Quantum Resources-Quantum Development Kit
description: 'Lär dig mer om Microsoft QDKs resurs uppskattning, som beräknar de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870556"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Uppskatta QDK-resurser (Quantum Development Kit)

Som namnet antyder `ResourcesEstimator` beräknar klassen de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator. Detta åstadkommer detta genom att köra åtgärden Quantum utan att faktiskt simulera status för en Quantum-dator. av den anledningen beräknar den resurser för frågor för Q # som använder tusentals qubits, förutsatt att den klassiska delen av koden körs på rimlig tid.

Resurs uppräkningen är byggd ovanpå [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), som ger en mer omfattande uppsättning mått och verktyg som hjälper dig att felsöka Q #-program.

## <a name="invoking-and-running-the-resources-estimator"></a>Anropar och kör resurs uppskattningen

Du kan använda resurs uppskattningen för att köra en Q #-åtgärd. Mer information finns i [sätt att köra ett Q #-program](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Anropar resurs uppskattningen från C # 

Precis som med andra mål datorer skapar du först en instans av `ResourceEstimator` klassen och skickar den som den första parametern för en åtgärds `Run` metod.

Observera att om klassen till skillnad från `QuantumSimulator` klassen `ResourceEstimator` implementerar inte <xref:System.IDisposable> gränssnittet, och därför behöver du inte ange det i en `using` instruktion.

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

Som exemplet visar `ResourcesEstimator` tillhandahåller `ToTSV()` metoden, som genererar en tabell med Tabbavgränsade värden (TSV). Du kan spara tabellen till en fil eller Visa den i konsolen för analys. Följande är ett exempel på utdata från föregående program:

```output
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
> En `ResourcesEstimator` instans återställer inte sina beräkningar vid varje körning. Om du använder samma instans för att köra en annan åtgärd sammanställs de nya resultaten med de befintliga resultaten. Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.

### <a name="invoking-the-resources-estimator-from-python"></a>Anropar resurs uppskattningen från python

Använd metoden [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q #-åtgärden:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Anropar resurs uppskattningen från kommando raden

När du kör ett Q #-program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange `ResourcesEstimator` mål datorn. Följande kommando kör ett program med hjälp av resurs uppskattningen: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Anropar resurs uppskattningen från Juptyer Notebooks

Använd SWEETIQ # Magic kommandot [% uppskattning](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q #-åtgärden.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Hämta beräknade data program mässigt

Förutom en TSV-tabell kan du program mässigt hämta de beräknade resurserna under körning via `Data` egenskapen för resurs uppskattningen. `Data`Egenskapen ger en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerat av måttets namn.

Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` `T` och åtgärder som `CNOT` används av en Q #-åtgärd:

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

Resurs uppskattningen spårar följande mått:

|Mått|Beskrivning|
|----|----|
|__CNOT__    |Antalet körningar av `CNOT` åtgärder (även kallat kontrollerade Pauli X-åtgärder).|
|__QubitClifford__ |Antalet körningar av alla enskilda qubit Clifford-och Pauli-åtgärder.|
|__Mått__    |Antalet körningar av alla mätningar.  |
|__R__    |Antalet körningar av en enskild-qubit rotations, exklusive `T` , Clifford och Pauli åtgärder.  |
|__T__    |Antalet körningar av `T` åtgärder och deras konjugat, inklusive `T` åtgärderna, T_x = H. T. H och T_y = hy. T. hy.  |
|__Djuplodande__|Den nedre gränserna för djupet i Quantum-kretsen som körs med åtgärden Q #. Djup måttet räknar som standard bara `T` grindar. Mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Bredd__    |Den nedre gränsen för maximalt antal allokerade qubits under körningen av Q #-åtgärden. Det kanske inte går att uppnå både __djup__ och __Bredd__ nedre gränser samtidigt.  |
|__BorrowedWidth__    |Det maximala antalet qubits som lånas inom Q #-åtgärden.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mått resultat

Du kan använda <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> från <xref:microsoft.quantum.diagnostics> namn området för att ge information om den förväntade sannolikheten för en mätnings åtgärd. Mer information finns i [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Se även

- [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Quantum Toffoli-Simulator](xref:microsoft.quantum.machines.toffoli-simulator)
- [Quantum, fullständig tillstånds Simulator](xref:microsoft.quantum.machines.full-state-simulator) 