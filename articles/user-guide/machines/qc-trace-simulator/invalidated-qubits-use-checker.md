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
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="db24e-103">Quantum trace Simulator: ogiltig användnings kontroll för qubits</span><span class="sxs-lookup"><span data-stu-id="db24e-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="db24e-104">Den invaliderade qubits use-kontrollen är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="db24e-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="db24e-105">Du kan använda den för att identifiera potentiella buggar i koden som orsakas av ogiltig qubits.</span><span class="sxs-lookup"><span data-stu-id="db24e-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="db24e-106">Ogiltig qubits</span><span class="sxs-lookup"><span data-stu-id="db24e-106">Invalid qubits</span></span>

<span data-ttu-id="db24e-107">Tänk på följande Q# kod för att illustrera de problem som upptäckts av den invaliderade qubits-användnings kontrollen:</span><span class="sxs-lookup"><span data-stu-id="db24e-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="db24e-108">När du tillämpar `H` åtgärden på `q[0]` , pekar den på en redan släppt qubit, vilket kan orsaka odefinierat beteende.</span><span class="sxs-lookup"><span data-stu-id="db24e-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="db24e-109">När den inverifierade qubits-användnings kontrollen är aktive rad, utlöses undantaget `InvalidatedQubitsUseCheckerException` om programmet tillämpar en åtgärd på en redan släppt qubit.</span><span class="sxs-lookup"><span data-stu-id="db24e-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="db24e-110">Mer information finns i <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="db24e-110">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="db24e-111">Anropar den invaliderade qubits-användnings kontrollen</span><span class="sxs-lookup"><span data-stu-id="db24e-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="db24e-112">För att köra Quantum trace-simulatorn med den invaliderade qubits-kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseInvalidatedQubitsUseChecker` egenskapen på **True** och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="db24e-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="db24e-113">Använda den invaliderade qubits-kontrollen i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="db24e-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="db24e-114">Följande är ett exempel på C#-värd program som använder Quantum trace simulator med den invaliderade qubits-användnings kontrollen aktive rad:</span><span class="sxs-lookup"><span data-stu-id="db24e-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="db24e-115">Se även</span><span class="sxs-lookup"><span data-stu-id="db24e-115">See also</span></span>

- <span data-ttu-id="db24e-116">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="db24e-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="db24e-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="db24e-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="db24e-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="db24e-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="db24e-119"><xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="db24e-119">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException> API reference.</span></span>
