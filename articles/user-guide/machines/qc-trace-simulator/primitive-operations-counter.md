---
title: Räknare för primitiva åtgärder
description: Lär dig mer om räknaren för primitiva Microsoft-QDK, som spårar antalet primitiva körningar som används av åtgärder i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275553"
---
# <a name="primitive-operations-counter"></a>Räknare för primitiva åtgärder  

`Primitive Operations Counter`Är en del av Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Det räknar antalet primitiva körningar som används av varje åtgärd som anropas i ett Quantum-program. Alla åtgärder från `Microsoft.Quantum.Intrinsic` uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Insamlad statistik sammanställs över kanterna på diagrammet för Operations-anropet. Nu räknar vi hur många `T` portar som behövs för att implementera `CCNOT` åtgärden. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Använda primitiva åtgärds räknare i ett C#-program

För att kontrol lera att `CCNOT` det verkligen krävs 7- `T` portar och som `ApplySampleWithCCNOT` Kör 8 `T` portar kan vi använda följande C#-kod:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Den första delen av programmet körs `ApplySampleWithCCNOT` . I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet T-portar som körs av `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

När `GetMetric` anropas med två typ parametrar returneras värdet för måttet som är kopplat till en specifik anrops diagram gräns. I vårt exempel `Primitive.CCNOT` kallas åtgärden i `ApplySampleWithCCNOT` och därför innehåller anrops diagrammet kanten `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

`CNOT`Vi kan lägga till följande rad för att få antalet portar som används:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Slutligen kan vi använda följande för att mata ut all statistik som samlas in av grind räknaren i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Se även ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
