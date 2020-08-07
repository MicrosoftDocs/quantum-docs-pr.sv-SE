---
title: Djup räknare – Quantum Development Kit
description: Lär dig mer om räknaren för Microsoft QDK-djupet, som använder Quantum trace Simulator för att samla in antalet djup för varje åtgärd som anropas i ett Q# program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c54f6fc479203d30c68c4958329605d4323f9ea
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868329"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Quantum trace Simulator: djup räknare

Djup räknaren är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).
Du kan använda den för att samla in antal som representerar den nedre gränserna för varje åtgärd som anropas i ett Quantum-program. 

## <a name="depth-values"></a>Djup värden

Som standard har alla åtgärder ett djup på **0** förutom `T` åtgärden, som har ett djup på **1**. Det innebär att som standard `T` beräknas endast djupet för åtgärder (vilket är ofta önskvärt). Djup räknaren räknar samman och samlar in statistik över alla kanter i åtgärdens [anrops diagram](https://en.wikipedia.org/wiki/Call_graph).

Alla <xref:microsoft.quantum.intrinsic> åtgärder uttrycks i form av en qubit rotation, <xref:microsoft.quantum.intrinsic.t> åtgärder, en qubit Clifford-åtgärd, <xref:microsoft.quantum.intrinsic.cnot> åtgärder och mätningar av multi-qubit Pauli observables. Användare kan ange djupet för varje primitiv åtgärd via `gateTimes` fältet i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Anropar djup räknaren

Om du vill köra en Quantum trace-simulator med djup räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ange `UseDepthCounter` egenskapen till **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Använda djup räknaren i ett C#-värd program

C#-exemplet som följer i det här avsnittet beräknar `T` djupet för `CCNOT` åtgärden, baserat på följande Q# exempel kod:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Om du vill kontrol lera att `CCNOT` har `T` djup **5** och `ApplySampleWithCCNOT` `T` djup **6**använder du följande C#-kod:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Den första delen av programmet körs `ApplySampleWithCCNOT` . Den andra delen använder [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta `T` djupet `CCNOT` och `ApplySampleWithCCNOT` . 

Slutligen kan du skriva ut all statistik som samlas in av djup räknaren i CSV-format med hjälp av följande:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Se även

- Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API-referensen.
