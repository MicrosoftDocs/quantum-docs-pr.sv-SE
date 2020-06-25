---
title: Kontroll av distinkt indata
description: 'Läs mer om Microsoft QDK DISTINCT Inputs Checker, som kontrollerar din Q #-kod för potentiella konflikter med delade qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275617"
---
# <a name="distinct-inputs-checker"></a>Kontroll av distinkt indata

`Distinct Inputs Checker`Är en del av Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Den är utformad för att identifiera potentiella buggar i koden. Tänk på följande i Q # Code för att illustrera de problem som upptäckts av det här paketet:

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

När användaren tittar på det här programmet antar de att ordningen i `op1` och `op2` anropas inte är beroende av `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits. Nu ska vi överväga ett exempel där den här åtgärden används:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Nu `op1` och `op2` är både hämtade med partiellt program och delar en qubit. När användaren anropar `ApplyBoth` i exemplet ovanför resultatet av åtgärden beror på ordningen på `op1` och `op2` inuti `ApplyBoth` . Detta är definitivt inte vad användaren förväntar sig att hända. `Distinct Inputs Checker`Dessa situationer identifieras när de aktive ras och kommer att utlösa `DistinctInputsCheckerException` . Mer information finns i API-dokumentationen för [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Använda den distinkta inmatnings kontrollen i C#-programmet

Följande är ett exempel på en C#-driv rutins kod för att använda Quantum Computer trace simulator med `Distinct Inputs Checker` aktiverat:

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

Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för `QCTraceSimulator` konstruktorn. När `useDistinctInputsChecker` är inställt på Sant `Distinct Inputs Checker` aktive ras. Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Se även

- Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
