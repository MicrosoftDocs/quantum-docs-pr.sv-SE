---
title: Räknare för primitiva åtgärder – Quantum Development Kit
description: Lär dig mer om räknaren för primitiva Microsoft-QDK, som använder Quantum trace Simulator för att spåra primitiva körningar som används av åtgärder i ett Q# program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868244"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Quantum trace Simulator: primitiva åtgärds räknare

Räknaren primitiv åtgärd är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Det räknar antalet primitiva körningar som används av varje åtgärd som anropas i ett Quantum-program. 

Alla <xref:microsoft.quantum.intrinsic> åtgärder uttrycks i form av en qubit rotation, T-åtgärder, qubit Clifford-åtgärder, CNOT-åtgärder och mätningar av multi-qubit Pauli observables. Räknaren för primitiva åtgärder sammanställer och samlar in statistik över alla kanter i åtgärdens [anrops diagram](https://en.wikipedia.org/wiki/Call_graph).

## <a name="invoking-the-primitive-operation-counter"></a>Anropar den primitiva åtgärds räknaren

Om du vill köra Quantum trace-simulatorn med den primitiva åtgärds räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ange `UsePrimitiveOperationsCounter` egenskapen till **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Använda den primitiva åtgärds räknaren i ett C#-värd program

C#-exemplet som följer i det här avsnittet räknar hur många <xref:microsoft.quantum.intrinsic.t> åtgärder som krävs för att implementera <xref:microsoft.quantum.intrinsic.ccnot> åtgärden, baserat på följande Q# exempel kod:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

`CCNOT`Använd följande C#-kod för att kontrol lera att kräver sju `T` åtgärder och som `ApplySampleWithCCNOT` Kör åtta `T` åtgärder:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Den första delen av programmet körs `ApplySampleWithCCNOT` . Den andra delen använder [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta antalet `T` åtgärder som körs av `ApplySampleWithCCNOT` : 

När du anropar `GetMetric` med två typ parametrar returnerar den värdet för måttet som är kopplat till en specifik anrops diagram gräns. I föregående exempel anropar programmet `Primitive.CCNOT` åtgärden i `ApplySampleWithCCNOT` och därför innehåller anrops diagrammet kanten `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

`CNOT`Lägg till följande rad för att hämta antalet åtgärder som används:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Slutligen kan du skriva ut all statistik som samlas in av räknaren primitiva åtgärder i CSV-format med hjälp av följande:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Se även

- Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API-referensen.