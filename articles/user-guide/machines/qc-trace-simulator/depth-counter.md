---
title: Djup räknare
description: Lär dig mer om räknaren för Microsoft QDK-djupet som samlar in antalet djup för varje åtgärd som anropas i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415276"
---
# <a name="depth-counter"></a><span data-ttu-id="07156-103">Djup räknare</span><span class="sxs-lookup"><span data-stu-id="07156-103">Depth Counter</span></span>

<span data-ttu-id="07156-104">`Depth Counter`Är en del av Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="07156-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="07156-105">Den används för att samla in antal som representerar den nedre gränserna för varje åtgärd som anropas i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="07156-105">It is used to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="07156-106">Alla åtgärder från <xref:microsoft.quantum.intrinsic> uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="07156-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="07156-107">Användare kan ange djupet för varje primitiv åtgärd via `gateTimes` fältet i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="07156-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="07156-108">Som standard har alla åtgärder djup 0, förutom T-porten som har djup 1.</span><span class="sxs-lookup"><span data-stu-id="07156-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="07156-109">Detta innebär att endast T-djupet beräknas (vilket är ofta önskvärt) som standard.</span><span class="sxs-lookup"><span data-stu-id="07156-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="07156-110">Insamlad statistik sammanställs över alla kanter i åtgärds anrops diagrammet.</span><span class="sxs-lookup"><span data-stu-id="07156-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="07156-111">Nu ska vi beräkna <xref:microsoft.quantum.intrinsic.t> djupet för <xref:microsoft.quantum.intrinsic.ccnot> åtgärden.</span><span class="sxs-lookup"><span data-stu-id="07156-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="07156-112">Vi kommer att använda följande exempel kod för Q #:</span><span class="sxs-lookup"><span data-stu-id="07156-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="07156-113">Använda djup räknare i ett C#-program</span><span class="sxs-lookup"><span data-stu-id="07156-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="07156-114">För att kontrol lera att `CCNOT` har `T` djup 5 och `ApplySampleWithCCNOT` `T` djup 6 kan vi använda följande C#-kod:</span><span class="sxs-lookup"><span data-stu-id="07156-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="07156-115">Den första delen av programmet körs `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="07156-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="07156-116">I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta `T` djupet `CCNOT` och `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="07156-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="07156-117">Slutligen kan vi använda följande för att mata ut all statistik som samlas in `Depth Counter` i CSV-format:</span><span class="sxs-lookup"><span data-stu-id="07156-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="07156-118">Se även</span><span class="sxs-lookup"><span data-stu-id="07156-118">See also</span></span> ##

- <span data-ttu-id="07156-119">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="07156-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
