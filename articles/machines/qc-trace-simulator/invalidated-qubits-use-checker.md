---
title: Ogiltig användnings kontroll för qubits | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863188"
---
# <a name="invalidated-qubits-use-checker"></a>Ogiltig användnings kontroll för qubits

`Invalidated Qubits Use Checker` är en del av Quantum Computer- [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) som har utformats för att identifiera potentiella buggar i koden. Överväg följande del av Q # Code för att illustrera de problem som upptäckts av `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

När `H` tillämpas på `q[0]` den pekar på en redan släppt qubit. Detta kan orsaka odefinierat beteende. När `Invalidated Qubits Use Checker` är aktive rad genereras undantags `InvalidatedQubitsUseCheckerException` om en åtgärd tillämpas på en redan släppt qubit. Mer information finns i API-dokumentationen för [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Använda den invaliderade qubits-kontrollen i ditt C# program

Följande är ett exempel på C# en driv rutins kod för att använda quantum Computer `Trace
Simulator` med `Invalidated Qubits Use Checker` aktiverat: 

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

Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för konstruktorn `QCTraceSimulator`. När `useInvalidatedQubitsUseChecker` är inställt på Sant är `Invalidated Qubits Use Checker` aktiverat. Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Se också ##

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
