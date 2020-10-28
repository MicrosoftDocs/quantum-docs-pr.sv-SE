---
title: Bredd räknare – Quantum Development Kit
description: Lär dig mer om Microsoft QDK width-räknaren, som använder Quantum trace Simulator för att räkna antalet qubits som tilldelas och lånas av åtgärder i ett Q# program.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691124"
---
# <a name="quantum-trace-simulator-width-counter"></a>Quantum trace Simulator: bredd räknare

Bredd räknaren är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Du kan använda det för att räkna antalet qubits som tilldelas och lånas av varje åtgärd i ett Q# program. Vissa primitiva åtgärder kan allokera extra qubits, till exempel multiplicera kontrollerade `X` åtgärder eller kontrollerade `T` åtgärder.

## <a name="invoking-the-width-counter"></a>Anropar bredd räknaren

Om du vill köra Quantum trace-simulatorn med bredd räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseWidthCounter` egenskapen på **True** och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Använda bredd räknaren i ett C#-värd program

C#-exemplet som följer i det här avsnittet beräknar antalet extra qubits som allokerats av implementeringen av en <xref:Microsoft.Quantum.Intrinsic.X> utförd multiplicering-åtgärd, baserat på följande Q# exempel kod:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Den multiplicerade kontrollerade <xref:Microsoft.Quantum.Intrinsic.X> åtgärden fungerar på totalt fem qubits, allokerar två [Hjälp qubits](xref:microsoft.quantum.glossary#ancilla)och har en ingångs bredd på **5** . Använd följande C#-program för att kontrol lera antalet:

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
