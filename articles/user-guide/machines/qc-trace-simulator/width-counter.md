---
title: Bredd räknare – Quantum Development Kit
description: 'Lär dig mer om Microsoft QDK width-räknaren, som använder Quantum trace Simulator för att räkna antalet qubits som tilldelas och lånas av åtgärder i ett Q #-program.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871531"
---
# <a name="quantum-trace-simulator-width-counter"></a>Quantum trace Simulator: bredd räknare

Bredd räknaren är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Du kan använda det för att räkna antalet qubits som tilldelas och lånas av varje åtgärd i ett Q #-program. Vissa primitiva åtgärder kan allokera extra qubits, till exempel multiplicera kontrollerade `X` åtgärder eller kontrollerade `T` åtgärder.

## <a name="invoking-the-width-counter"></a>Anropar bredd räknaren

Om du vill köra Quantum trace-simulatorn med bredd räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseWidthCounter` egenskapen på **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Använda bredd räknaren i ett C#-värd program

C#-exemplet som följer i det här avsnittet beräknar antalet extra qubits som allokerats av implementeringen av en <xref:microsoft.quantum.intrinsic.x> utförd multiplicering-åtgärd baserat på följande Q # exempel kod:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Den multiplicerade kontrollerade <xref:microsoft.quantum.intrinsic.x> åtgärden fungerar på totalt fem qubits, allokerar två [Hjälp qubits](xref:microsoft.quantum.glossary#ancilla)och har en ingångs bredd på **5**. Använd följande C#-program för att kontrol lera antalet:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

Den första delen av programmet kör `ApplyMultiControlledX` åtgärden. I den andra delen används [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta antalet allokerade qubits samt antalet qubits som `Controlled X` åtgärden tog emot som inmatade. 

Slutligen kan du skriva ut all statistik som samlas in av bredd räknaren i CSV-format med följande:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Se även

- Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API-referensen.
