---
title: Ogiltig användnings kontroll för qubits | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820886"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="0251f-103">Ogiltig användnings kontroll för qubits</span><span class="sxs-lookup"><span data-stu-id="0251f-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="0251f-104">`Invalidated Qubits Use Checker` är en del av Quantum Computer- [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) som har utformats för att identifiera potentiella buggar i koden.</span><span class="sxs-lookup"><span data-stu-id="0251f-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="0251f-105">Överväg följande del av Q # Code för att illustrera de problem som upptäckts av `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="0251f-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="0251f-106">När `H` tillämpas på `q[0]` den pekar på en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="0251f-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="0251f-107">Detta kan orsaka odefinierat beteende.</span><span class="sxs-lookup"><span data-stu-id="0251f-107">This can cause undefined behavior.</span></span> <span data-ttu-id="0251f-108">När `Invalidated Qubits Use Checker` är aktive rad genereras undantags `InvalidatedQubitsUseCheckerException` om en åtgärd tillämpas på en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="0251f-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="0251f-109">Mer information finns i API-dokumentationen för [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="0251f-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="0251f-110">Använda den invaliderade qubits-kontrollen i ditt C# program</span><span class="sxs-lookup"><span data-stu-id="0251f-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="0251f-111">Följande är ett exempel på C# en driv rutins kod för att använda quantum Computer `Trace
Simulator` med `Invalidated Qubits Use Checker` aktiverat:</span><span class="sxs-lookup"><span data-stu-id="0251f-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="0251f-112">Klassen `QCTraceSimulatorConfiguration` lagrar konfigurationen av Quantum Computer trace Simulator och kan anges som ett argument för konstruktorn `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="0251f-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="0251f-113">När `useInvalidatedQubitsUseChecker` är inställt på Sant är `Invalidated Qubits Use Checker` aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0251f-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="0251f-114">Mer information finns i API-dokumentationen för [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) och [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0251f-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="0251f-115">Se också</span><span class="sxs-lookup"><span data-stu-id="0251f-115">See also</span></span> ##

- <span data-ttu-id="0251f-116">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="0251f-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
