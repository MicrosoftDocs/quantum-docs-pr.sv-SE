---
title: Djup räknare
description: Lär dig mer om räknaren för Microsoft QDK-djupet som samlar in antalet djup för varje åtgärd som anropas i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275630"
---
# <a name="depth-counter"></a>Djup räknare

`Depth Counter`Är en del av Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).
Det används för att samla in antalet djup för varje åtgärd som anropas i ett Quantum-program. Alla åtgärder från <xref:microsoft.quantum.intrinsic> uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Användare kan ange djupet för varje primitiv åtgärd via `gateTimes` fältet i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Som standard har alla åtgärder djup 0, förutom T-porten som har djup 1. Detta innebär att endast T-djupet beräknas (vilket är ofta önskvärt) som standard. Insamlad statistik sammanställs över alla kanter i åtgärds anrops diagrammet. 

Nu ska vi beräkna <xref:microsoft.quantum.intrinsic.t> djupet för <xref:microsoft.quantum.intrinsic.ccnot> åtgärden. Vi kommer att använda följande exempel kod för Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Använda djup räknare i ett C#-program

För att kontrol lera att `CCNOT` har `T` djup 5 och `ApplySampleWithCCNOT` `T` djup 6 kan vi använda följande C#-kod:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Den första delen av programmet körs `ApplySampleWithCCNOT` . I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta `T` djupet `CCNOT` och `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Slutligen kan vi använda följande för att mata ut all statistik som samlas in `Depth Counter` i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Se även ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
