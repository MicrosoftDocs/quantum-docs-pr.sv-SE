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
# <a name="distinct-inputs-checker"></a><span data-ttu-id="cee7e-103">Kontroll av distinkt indata</span><span class="sxs-lookup"><span data-stu-id="cee7e-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="cee7e-104">`Distinct Inputs Checker`Är en del av Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="cee7e-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="cee7e-105">Den är utformad för att identifiera potentiella buggar i koden.</span><span class="sxs-lookup"><span data-stu-id="cee7e-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="cee7e-106">Tänk på följande i Q # Code för att illustrera de problem som upptäckts av det här paketet:</span><span class="sxs-lookup"><span data-stu-id="cee7e-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="cee7e-107">När användaren tittar på det här programmet antar de att ordningen i `op1` och `op2` anropas inte är beroende av `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits.</span><span class="sxs-lookup"><span data-stu-id="cee7e-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="cee7e-108">Nu ska vi överväga ett exempel där den här åtgärden används:</span><span class="sxs-lookup"><span data-stu-id="cee7e-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="cee7e-109">Nu `op1` och `op2` är både hämtade med partiellt program och delar en qubit.</span><span class="sxs-lookup"><span data-stu-id="cee7e-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="cee7e-110">När användaren anropar `ApplyBoth` i exemplet ovanför resultatet av åtgärden beror på ordningen på `op1` och `op2` inuti `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="cee7e-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="cee7e-111">Detta är definitivt inte vad användaren förväntar sig att hända.</span><span class="sxs-lookup"><span data-stu-id="cee7e-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="cee7e-112">`Distinct Inputs Checker`Dessa situationer identifieras när de aktive ras och kommer att utlösa `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="cee7e-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="cee7e-113">Mer information finns i API-dokumentationen för [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="cee7e-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="cee7e-114">Använda den distinkta inmatnings kontrollen i C#-programmet</span><span class="sxs-lookup"><span data-stu-id="cee7e-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="cee7e-115">Följande är ett exempel på en C#-driv rutins kod för att använda Quantum Computer trace simulator med `Distinct Inputs Checker` aktiverat:</span><span class="sxs-lookup"><span data-stu-id="cee7e-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="cee7e-116">Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för `QCTraceSimulator` konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="cee7e-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="cee7e-117">När `useDistinctInputsChecker` är inställt på Sant `Distinct Inputs Checker` aktive ras.</span><span class="sxs-lookup"><span data-stu-id="cee7e-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="cee7e-118">Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="cee7e-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="cee7e-119">Se även</span><span class="sxs-lookup"><span data-stu-id="cee7e-119">See also</span></span>

- <span data-ttu-id="cee7e-120">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="cee7e-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
