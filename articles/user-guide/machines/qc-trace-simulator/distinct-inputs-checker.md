---
title: Distinkta inmatnings kontroll – Quantum Development Kit
description: 'Läs mer om Microsoft QDK DISTINCT Inputs Checker, som använder Quantum trace Simulator för att kontrol lera din Q #-kod för potentiella konflikter med delade qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871152"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="0502f-103">Quantum trace Simulator: distinkt inmatnings kontroll</span><span class="sxs-lookup"><span data-stu-id="0502f-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="0502f-104">Kontrollen distinkta indata är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="0502f-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0502f-105">Du kan använda den för att identifiera potentiella buggar i koden som orsakas av konflikter med delade qubits.</span><span class="sxs-lookup"><span data-stu-id="0502f-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="0502f-106">Konflikter med delade qubits</span><span class="sxs-lookup"><span data-stu-id="0502f-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="0502f-107">Tänk på följande i Q # Code för att illustrera de problem som upptäckts av den distinkta indata-kontrollen:</span><span class="sxs-lookup"><span data-stu-id="0502f-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="0502f-108">När du tittar på det här programmet kan du anta att den ordning som den anropar `op1` `op2` , och inte spelar någon roll, eftersom `q1` och `q2` är olika qubits och åtgärder som fungerar på olika qubits.</span><span class="sxs-lookup"><span data-stu-id="0502f-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="0502f-109">Titta nu på det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="0502f-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="0502f-110">Observera att `op1` och `op2` båda är hämtade med delar av program och delar en qubit.</span><span class="sxs-lookup"><span data-stu-id="0502f-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="0502f-111">När du anropar `ApplyBoth` i det här exemplet beror resultatet av åtgärden på ordningen på `op1` och `op2` `ApplyBoth` inte vad du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="0502f-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="0502f-112">När du aktiverar den distinkta inmatnings kontrollen identifierar den sådana situationer och returnerar en `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="0502f-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="0502f-113">Mer information finns <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> i i Q # API-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0502f-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="0502f-114">Anropar den distinkta inmatnings kontrollen</span><span class="sxs-lookup"><span data-stu-id="0502f-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="0502f-115">Om du vill köra en Quantum trace-simulator med den distinkta ingångs kontrollen måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseDistinctInputsChecker` egenskapen på **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="0502f-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="0502f-116">Använda den distinkta inmatnings kontrollen i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="0502f-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="0502f-117">Följande är ett exempel på ett C#-värdprogram som använder Quantum trace simulator med den distinkta ingångs kontrollen aktive rad:</span><span class="sxs-lookup"><span data-stu-id="0502f-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0502f-118">Se även</span><span class="sxs-lookup"><span data-stu-id="0502f-118">See also</span></span>

- <span data-ttu-id="0502f-119">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="0502f-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="0502f-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="0502f-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="0502f-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="0502f-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="0502f-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="0502f-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
