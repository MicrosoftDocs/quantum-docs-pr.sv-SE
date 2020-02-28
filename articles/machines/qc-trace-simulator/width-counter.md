---
title: Bredd räknare
description: Lär dig mer om Microsoft QDK width-räknaren, som räknar antalet qubits som tilldelas och lånas ut av varje åtgärd i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907094"
---
# <a name="width-counter"></a>Bredd räknare

`Width Counter` räknar antalet allokerade och lånade av varje åtgärd.
Alla åtgärder från `Microsoft.Quantum.Intrinsic` namn området uttrycks i förhållande till enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables. Några av de primitiva åtgärderna kan allokera extra qubits. Du kan till exempel multiplicera kontrollerade `X` portar eller kontrollerade `T` portar. Låt oss beräkna antalet extra qubits som allokerats av implementeringen av en multiplicering-kontrollerad `X`-grind:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Använda en bredd räknare i C# ett program

Om du multiplicerar kontrollerade `X` hur du får totalt 5 qubits allokeras 2 hjälp qubits och dess ingångs bredd är 5. Vi kan använda följande C# program för att kontrol lera att detta är fallet:

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

Den första delen av programmet körs `ApplyMultiControlledX`. I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet allokerade qubits samt antalet qubits som styrs `X` togs emot som inaktuella inmatade. 

Slutligen kan vi använda följande för att mata ut all statistik som samlas in med en bredd räknare i CSV-format:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Se även ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
