---
title: Kontroll av distinkt indata
description: 'Läs mer om Microsoft QDK DISTINCT Inputs Checker, som kontrollerar din Q #-kod för potentiella konflikter med delade qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907111"
---
# <a name="distinct-inputs-checker"></a>Kontroll av distinkt indata

`Distinct Inputs Checker` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Den är utformad för att identifiera potentiella buggar i koden. Tänk på följande i Q # Code för att illustrera de problem som upptäckts av det här paketet:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

När användaren tittar på det här programmet antar de att ordningen i vilken `op1` och `op2` anropas inte beror på att `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits. Nu ska vi överväga ett exempel där den här åtgärden används:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Nu `op1` och `op2` hämtas både genom att använda delar av programmet och dela en qubit. När användaren anropar `ApplyBoth` i exemplet ovan beror resultatet av åtgärden på `op1` och `op2` i `ApplyBoth`. Detta är definitivt inte vad användaren förväntar sig att hända. `Distinct Inputs Checker` identifierar sådana situationer när de aktive ras och kommer att utlösa `DistinctInputsCheckerException`. Mer information finns i API-dokumentationen för [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Använda den distinkta inmatnings C# kontrollen i ditt program

Följande är ett exempel på C# en driv rutins kod för användning av Quantum Computer trace simulator med `Distinct Inputs Checker` aktiverat:

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för konstruktorn `QCTraceSimulator`. När `useDistinctInputsChecker` är inställt på Sant är `Distinct Inputs Checker` aktiverat. Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Se även

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
