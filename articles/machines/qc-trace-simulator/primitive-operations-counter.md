---
title: Räknare för primitiva åtgärder | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820427"
---
# <a name="primitive-operations-counter"></a>Räknare för primitiva åtgärder  

`Primitive Operations Counter` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Det räknar antalet primitiva körningar som används av varje åtgärd som anropas i ett Quantum-program. Alla åtgärder från `Microsoft.Quantum.Intrinsic` uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Insamlad statistik sammanställs över kanterna på diagrammet för Operations-anropet. Nu räknar vi hur många `T` portar som behövs för att implementera `CCNOT`s åtgärden. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Använda primitiva åtgärds räknare i C# ett program

För att kontrol lera att `CCNOT` verkligen kräver 7 `T` portar och att `ApplySampleWithCCNOT` kör 8 `T` portar kan vi använda följande C# kod:

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

Den första delen av programmet körs `ApplySampleWithCCNOT`. I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet T-portar som körs av `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

När `GetMetric` anropas med två typ parametrar returneras värdet för måttet som är kopplat till en specifik anrops kurva. I vårt exempel åtgärds `Primitive.CCNOT` anropas i `ApplySampleWithCCNOT` och därför innehåller anrops diagrammet gränsen `<Primitive.CCNOT, ApplySampleWithCCNOT>`. 

Vi kan lägga till följande rad för att få antalet `CNOT` portar som används:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Slutligen kan vi använda följande för att mata ut all statistik som samlas in av grind räknaren i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Se också ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
