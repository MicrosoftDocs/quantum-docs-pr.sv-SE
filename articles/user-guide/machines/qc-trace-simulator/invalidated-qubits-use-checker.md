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
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="6932f-103">Ogiltig användnings kontroll för qubits</span><span class="sxs-lookup"><span data-stu-id="6932f-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="6932f-104">`Invalidated Qubits Use Checker`Är en del av Quantum Computer- [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) som är utformad för att identifiera potentiella buggar i koden.</span><span class="sxs-lookup"><span data-stu-id="6932f-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="6932f-105">Överväg följande del av Q # Code för att illustrera de problem som upptäckts av `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="6932f-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="6932f-106">När `H` tillämpas på `q[0]` den pekar en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="6932f-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="6932f-107">Detta kan orsaka odefinierat beteende.</span><span class="sxs-lookup"><span data-stu-id="6932f-107">This can cause undefined behavior.</span></span> <span data-ttu-id="6932f-108">När `Invalidated Qubits Use Checker` är aktive rad kommer undantaget att `InvalidatedQubitsUseCheckerException` genereras om en åtgärd tillämpas på en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="6932f-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="6932f-109">Mer information finns i API-dokumentationen för [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="6932f-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="6932f-110">Använda den invaliderade qubits-kontrollen i C#-programmet</span><span class="sxs-lookup"><span data-stu-id="6932f-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="6932f-111">Följande är ett exempel på en C#-driv rutins kod för att använda den Quantum datorn `Trace
Simulator` med den `Invalidated Qubits Use Checker` aktiverade:</span><span class="sxs-lookup"><span data-stu-id="6932f-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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

<span data-ttu-id="6932f-112">Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för `QCTraceSimulator` konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="6932f-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="6932f-113">När `useInvalidatedQubitsUseChecker` är inställt på Sant `Invalidated Qubits Use Checker` aktive ras.</span><span class="sxs-lookup"><span data-stu-id="6932f-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="6932f-114">Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="6932f-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="6932f-115">Se även</span><span class="sxs-lookup"><span data-stu-id="6932f-115">See also</span></span> ##

- <span data-ttu-id="6932f-116">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="6932f-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
