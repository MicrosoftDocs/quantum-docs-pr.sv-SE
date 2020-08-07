---
title: Distinkta inmatnings kontroll – Quantum Development Kit
description: Läs mer om Microsoft QDK DISTINCT Inputs Checker, som använder Quantum trace Simulator för att kontrol lera din Q# kod för potentiella konflikter med delade qubits.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868278"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="02788-103">Quantum trace Simulator: distinkt inmatnings kontroll</span><span class="sxs-lookup"><span data-stu-id="02788-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="02788-104">Kontrollen distinkta indata är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="02788-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="02788-105">Du kan använda den för att identifiera potentiella buggar i koden som orsakas av konflikter med delade qubits.</span><span class="sxs-lookup"><span data-stu-id="02788-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="02788-106">Konflikter med delade qubits</span><span class="sxs-lookup"><span data-stu-id="02788-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="02788-107">Överväg följande Q# kod avsnitt för att illustrera de problem som upptäckts av den distinkta indata-kontrollen:</span><span class="sxs-lookup"><span data-stu-id="02788-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="02788-108">När du tittar på det här programmet kan du anta att den ordning som den anropar `op1` `op2` , och inte spelar någon roll, eftersom `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits.</span><span class="sxs-lookup"><span data-stu-id="02788-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="02788-109">Titta nu på det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="02788-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="02788-110">Observera att `op1` och `op2` båda är hämtade med delar av program och delar en qubit.</span><span class="sxs-lookup"><span data-stu-id="02788-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="02788-111">När du anropar `ApplyBoth` i det här exemplet beror resultatet av åtgärden på ordningen på `op1` och `op2` `ApplyBoth` inte vad du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="02788-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="02788-112">När du aktiverar den distinkta inmatnings kontrollen identifierar den sådana situationer och returnerar en `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="02788-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="02788-113">Mer information finns <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> i i API- Q# biblioteket.</span><span class="sxs-lookup"><span data-stu-id="02788-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="02788-114">Anropar den distinkta inmatnings kontrollen</span><span class="sxs-lookup"><span data-stu-id="02788-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="02788-115">Om du vill köra en Quantum trace-simulator med den distinkta ingångs kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseDistinctInputsChecker` egenskapen på **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="02788-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="02788-116">Använda den distinkta inmatnings kontrollen i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="02788-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="02788-117">Följande är ett exempel på ett C#-värdprogram som använder Quantum trace simulator med den distinkta ingångs kontrollen aktive rad:</span><span class="sxs-lookup"><span data-stu-id="02788-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="02788-118">Se även</span><span class="sxs-lookup"><span data-stu-id="02788-118">See also</span></span>

- <span data-ttu-id="02788-119">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="02788-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="02788-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="02788-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="02788-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="02788-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="02788-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="02788-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
