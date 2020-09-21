---
title: Distinkta inmatnings kontroll – Quantum Development Kit
description: Läs mer om Microsoft QDK DISTINCT Inputs Checker, som använder Quantum trace Simulator för att kontrol lera din Q# kod för potentiella konflikter med delade qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833462"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Quantum trace Simulator: distinkt inmatnings kontroll

Kontrollen distinkta indata är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Du kan använda den för att identifiera potentiella buggar i koden som orsakas av konflikter med delade qubits. 

## <a name="conflicts-with-shared-qubits"></a>Konflikter med delade qubits

Överväg följande Q# kod avsnitt för att illustrera de problem som upptäckts av den distinkta indata-kontrollen:

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

När du tittar på det här programmet kan du anta att den ordning som den anropar `op1` `op2` , och inte spelar någon roll, eftersom `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits. 

Titta nu på det här exemplet:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Observera att `op1` och `op2` båda är hämtade med delar av program och delar en qubit. När du anropar `ApplyBoth` i det här exemplet beror resultatet av åtgärden på ordningen på `op1` och `op2` `ApplyBoth` inte vad du förväntar dig. När du aktiverar den distinkta inmatnings kontrollen identifierar den sådana situationer och returnerar en `DistinctInputsCheckerException` . Mer information finns <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> i i API- Q# biblioteket.

## <a name="invoking-the-distinct-inputs-checker"></a>Anropar den distinkta inmatnings kontrollen

Om du vill köra en Quantum trace-simulator med den distinkta ingångs kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseDistinctInputsChecker` egenskapen på **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Använda den distinkta inmatnings kontrollen i ett C#-värd program

Följande är ett exempel på ett C#-värdprogram som använder Quantum trace simulator med den distinkta ingångs kontrollen aktive rad:

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
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
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API-referensen.
