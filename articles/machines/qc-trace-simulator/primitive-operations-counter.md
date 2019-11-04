---
title: Räknare för primitiva åtgärder | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över Quantum Computer trace Simulator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184890"
---
# <a name="primitive-operations-counter"></a>Räknare för primitiva åtgärder  

`Primitive Operations Counter` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Det räknar antalet primitiva körningar som används av varje åtgärd som anropas i ett Quantum-program. Alla åtgärder från `Microsoft.Quantum.Primitive` uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Insamlad statistik sammanställs över kanterna på diagrammet för Operations-anropet. Nu räknar vi hur många `T` portar som behövs för att implementera `CCNOT`s åtgärden. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Använda primitiva åtgärds räknare i C# ett program

För att kontrol lera att `CCNOT` verkligen kräver 7 `T` portar och att `CCNOTDriver` kör 8 `T` portar kan vi använda följande C# kod:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Den första delen av programmet körs `CCNOTDriver`. I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet T-portar som körs av `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

När `GetMetric` anropas med två typ parametrar returneras värdet för måttet som är kopplat till en specifik anrops kurva. I vårt exempel åtgärds `Primitive.CCNOT` anropas i `CCNOTDriver` och därför innehåller anrops diagrammet gränsen `<Primitive.CCNOT,CCNOTDriver>`. 

Vi kan lägga till följande rad för att få antalet `CNOT` portar som används:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Slutligen kan vi använda följande för att mata ut all statistik som samlas in av grind räknaren i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Se också ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
