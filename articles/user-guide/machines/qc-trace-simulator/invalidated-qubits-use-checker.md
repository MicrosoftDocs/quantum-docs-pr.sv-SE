---
title: Ogiltig qubits användnings kontroll – Quantum Development Kit
description: Lär dig mer om den invaliderade qubits i Microsoft QDK, som använder Quantum trace Simulator för att kontrol lera Q# koden för potentiellt ogiltig qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9014097ace7c9f19d93a92372da40f71fa7f87ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858612"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Quantum trace Simulator: ogiltig användnings kontroll för qubits

Den invaliderade qubits use-kontrollen är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Du kan använda den för att identifiera potentiella buggar i koden som orsakas av ogiltig qubits. 

## <a name="invalid-qubits"></a>Ogiltig qubits

Tänk på följande Q# kod för att illustrera de problem som upptäckts av den invaliderade qubits-användnings kontrollen:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

När du tillämpar `H` åtgärden på `q[0]` , pekar den på en redan släppt qubit, vilket kan orsaka odefinierat beteende. När den inverifierade qubits-användnings kontrollen är aktive rad, utlöses undantaget `InvalidatedQubitsUseCheckerException` om programmet tillämpar en åtgärd på en redan släppt qubit. Mer information finns i <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Anropar den invaliderade qubits-användnings kontrollen

För att köra Quantum trace-simulatorn med den invaliderade qubits-kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseInvalidatedQubitsUseChecker` egenskapen på **True** och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Använda den invaliderade qubits-kontrollen i ett C#-värd program

Följande är ett exempel på C#-värd program som använder Quantum trace simulator med den invaliderade qubits-användnings kontrollen aktive rad: 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Se även

- Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.
- <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>API-referensen.
