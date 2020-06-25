---
title: Kontroll av användning av upphävda kvantbitar
description: 'Lär dig mer om den invaliderade qubits use-kontrollen i Microsoft QDK, som kontrollerar din Q #-kod för potentiellt ogiltiga qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275569"
---
# <a name="invalidated-qubits-use-checker"></a>Ogiltig användnings kontroll för qubits

`Invalidated Qubits Use Checker`Är en del av Quantum Computer- [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) som är utformad för att identifiera potentiella buggar i koden. Överväg följande del av Q # Code för att illustrera de problem som upptäckts av `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

När `H` tillämpas på `q[0]` den pekar en redan släppt qubit. Detta kan orsaka odefinierat beteende. När `Invalidated Qubits Use Checker` är aktive rad kommer undantaget att `InvalidatedQubitsUseCheckerException` genereras om en åtgärd tillämpas på en redan släppt qubit. Mer information finns i API-dokumentationen för [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Använda den invaliderade qubits-kontrollen i C#-programmet

Följande är ett exempel på en C#-driv rutins kod för att använda den Quantum datorn `Trace
Simulator` med den `Invalidated Qubits Use Checker` aktiverade: 

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för `QCTraceSimulator` konstruktorn. När `useInvalidatedQubitsUseChecker` är inställt på Sant `Invalidated Qubits Use Checker` aktive ras. Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Se även ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
