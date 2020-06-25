---
title: Bredd räknare
description: Lär dig mer om Microsoft QDK width-räknaren, som räknar antalet qubits som tilldelas och lånas ut av varje åtgärd i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275566"
---
# <a name="width-counter"></a>Bredd räknare

`Width Counter`Antalet qubits som tilldelas och lånas av varje åtgärd.
Alla åtgärder från `Microsoft.Quantum.Intrinsic` namn området uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Några av de primitiva åtgärderna kan allokera extra qubits. Du kan till exempel multiplicera kontrollerade `X` grindar eller kontrollerade `T` grindar. Låt oss beräkna antalet extra qubits som allokerats av implementeringen av en multiplicering-kontrollerad `X` grind:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Använda en bredd räknare i ett C#-program

Multiplicering som styrs `X` på totalt 5 qubits kommer att allokera 2 hjälp qubits och dess ingångs bredd är 5. Vi kan använda följande C#-program för att kontrol lera att detta är fallet:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

Den första delen av programmet körs `ApplyMultiControlledX` . I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet allokerade qubits samt antalet qubits som har kontroller ATS som inaktuella `X` . 

Slutligen kan vi använda följande för att mata ut all statistik som samlas in med en bredd räknare i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Se även ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
