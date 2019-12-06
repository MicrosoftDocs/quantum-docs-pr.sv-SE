---
title: Kontroll av distinkta ingångar | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: ce3f156a84a4509781a74c9276b953c79670a756
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864312"
---
# <a name="distinct-inputs-checker"></a>Kontroll av distinkt indata

`Distinct Inputs Checker` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Den är utformad för att identifiera potentiella buggar i koden. Tänk på följande i Q # Code för att illustrera de problem som upptäckts av det här paketet:

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

När användaren tittar på det här programmet antar de att ordningen i vilken `op1` och `op2` anropas inte beror på att `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits. Nu ska vi överväga ett exempel där den här åtgärden används:

```qsharp
operation CapturedQubits () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

Nu `op1` och `op2` hämtas både genom att använda delar av programmet och dela en qubit. När användaren anropar `DoBoth` i exemplet ovan beror resultatet av åtgärden på `op1` och `op2` i `DoBoth`. Detta är definitivt inte vad användaren förväntar sig att hända. `Distinct Inputs Checker` identifierar sådana situationer när de aktive ras och kommer att utlösa `DistinctInputsCheckerException`. Mer information finns i API-dokumentationen för [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

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

## <a name="see-also"></a>Se också

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
