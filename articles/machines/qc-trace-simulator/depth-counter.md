---
title: Djup räknare | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över Quantum Computer trace Simulator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184907"
---
# <a name="depth-counter"></a>Djup räknare

`Depth Counter` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).
Det används för att samla in antalet djup för varje åtgärd som anropas i ett Quantum-program. Alla åtgärder från <xref:microsoft.quantum.intrinsic> uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Användare kan ställa in djupet för var och en av de primitiva åtgärderna via `gateTimes` fältet i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Som standard har alla åtgärder djup 0, förutom T-porten som har djup 1. Detta innebär att endast T-djupet beräknas (vilket är ofta önskvärt) som standard. Insamlad statistik sammanställs över alla kanter i åtgärds anrops diagrammet. 

Nu ska vi beräkna <xref:microsoft.quantum.intrinsic.t> djupet i <xref:microsoft.quantum.intrinsic.ccnot>s åtgärden. Vi kommer att använda följande Q #-driv rutins kod: 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Använda djup räknare i ett C# program

För att kontrol lera att `CCNOT` har `T` djup 5 och `CCNOTDriver` har `T` djup 6 kan vi använda C# följande kod:

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Den första delen av programmet körs `CCNOTDriver`. I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta `T` djupet för `CCNOT` och `CCNOTDriver`: 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Slutligen kan vi använda följande för att mata ut all statistik som samlas in av `Depth Counter` i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Se också ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
