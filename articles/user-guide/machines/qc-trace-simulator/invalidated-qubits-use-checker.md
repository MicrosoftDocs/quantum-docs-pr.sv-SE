---
title: Ogiltig qubits användnings kontroll – Quantum Development Kit
description: Lär dig mer om den invaliderade qubits i Microsoft QDK, som använder Quantum trace Simulator för att kontrol lera Q# koden för potentiellt ogiltig qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836003"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="6696a-103">Quantum trace Simulator: ogiltig användnings kontroll för qubits</span><span class="sxs-lookup"><span data-stu-id="6696a-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="6696a-104">Den invaliderade qubits use-kontrollen är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="6696a-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6696a-105">Du kan använda den för att identifiera potentiella buggar i koden som orsakas av ogiltig qubits.</span><span class="sxs-lookup"><span data-stu-id="6696a-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="6696a-106">Ogiltig qubits</span><span class="sxs-lookup"><span data-stu-id="6696a-106">Invalid qubits</span></span>

<span data-ttu-id="6696a-107">Tänk på följande Q# kod för att illustrera de problem som upptäckts av den invaliderade qubits-användnings kontrollen:</span><span class="sxs-lookup"><span data-stu-id="6696a-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="6696a-108">När du tillämpar `H` åtgärden på `q[0]` , pekar den på en redan släppt qubit, vilket kan orsaka odefinierat beteende.</span><span class="sxs-lookup"><span data-stu-id="6696a-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="6696a-109">När den inverifierade qubits-användnings kontrollen är aktive rad, utlöses undantaget `InvalidatedQubitsUseCheckerException` om programmet tillämpar en åtgärd på en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="6696a-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="6696a-110">Mer information finns i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="6696a-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="6696a-111">Anropar den invaliderade qubits-användnings kontrollen</span><span class="sxs-lookup"><span data-stu-id="6696a-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="6696a-112">För att köra Quantum trace-simulatorn med den invaliderade qubits-kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseInvalidatedQubitsUseChecker` egenskapen på **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="6696a-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="6696a-113">Använda den invaliderade qubits-kontrollen i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="6696a-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="6696a-114">Följande är ett exempel på C#-värd program som använder Quantum trace simulator med den invaliderade qubits-användnings kontrollen aktive rad:</span><span class="sxs-lookup"><span data-stu-id="6696a-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="6696a-115">Se även</span><span class="sxs-lookup"><span data-stu-id="6696a-115">See also</span></span>

- <span data-ttu-id="6696a-116">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="6696a-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="6696a-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="6696a-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="6696a-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="6696a-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="6696a-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="6696a-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>