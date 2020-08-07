---
title: Djup räknare – Quantum Development Kit
description: Lär dig mer om räknaren för Microsoft QDK-djupet, som använder Quantum trace Simulator för att samla in antalet djup för varje åtgärd som anropas i ett Q# program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c54f6fc479203d30c68c4958329605d4323f9ea
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868329"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="d118f-103">Quantum trace Simulator: djup räknare</span><span class="sxs-lookup"><span data-stu-id="d118f-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="d118f-104">Djup räknaren är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="d118f-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="d118f-105">Du kan använda den för att samla in antal som representerar den nedre gränserna för varje åtgärd som anropas i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="d118f-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="d118f-106">Djup värden</span><span class="sxs-lookup"><span data-stu-id="d118f-106">Depth values</span></span>

<span data-ttu-id="d118f-107">Som standard har alla åtgärder ett djup på **0** förutom `T` åtgärden, som har ett djup på **1**.</span><span class="sxs-lookup"><span data-stu-id="d118f-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="d118f-108">Det innebär att som standard `T` beräknas endast djupet för åtgärder (vilket är ofta önskvärt).</span><span class="sxs-lookup"><span data-stu-id="d118f-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="d118f-109">Djup räknaren räknar samman och samlar in statistik över alla kanter i åtgärdens [anrops diagram](https://en.wikipedia.org/wiki/Call_graph).</span><span class="sxs-lookup"><span data-stu-id="d118f-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="d118f-110">Alla <xref:microsoft.quantum.intrinsic> åtgärder uttrycks i form av en qubit rotation, <xref:microsoft.quantum.intrinsic.t> åtgärder, en qubit Clifford-åtgärd, <xref:microsoft.quantum.intrinsic.cnot> åtgärder och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="d118f-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="d118f-111">Användare kan ange djupet för varje primitiv åtgärd via `gateTimes` fältet i <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="d118f-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="d118f-112">Anropar djup räknaren</span><span class="sxs-lookup"><span data-stu-id="d118f-112">Invoking the depth counter</span></span>

<span data-ttu-id="d118f-113">Om du vill köra en Quantum trace-simulator med djup räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ange `UseDepthCounter` egenskapen till **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="d118f-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="d118f-114">Använda djup räknaren i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="d118f-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="d118f-115">C#-exemplet som följer i det här avsnittet beräknar `T` djupet för `CCNOT` åtgärden, baserat på följande Q# exempel kod:</span><span class="sxs-lookup"><span data-stu-id="d118f-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="d118f-116">Om du vill kontrol lera att `CCNOT` har `T` djup **5** och `ApplySampleWithCCNOT` `T` djup **6**använder du följande C#-kod:</span><span class="sxs-lookup"><span data-stu-id="d118f-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="d118f-117">Den första delen av programmet körs `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="d118f-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="d118f-118">Den andra delen använder [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta `T` djupet `CCNOT` och `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="d118f-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="d118f-119">Slutligen kan du skriva ut all statistik som samlas in av djup räknaren i CSV-format med hjälp av följande:</span><span class="sxs-lookup"><span data-stu-id="d118f-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="d118f-120">Se även</span><span class="sxs-lookup"><span data-stu-id="d118f-120">See also</span></span>

- <span data-ttu-id="d118f-121">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="d118f-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="d118f-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="d118f-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="d118f-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="d118f-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="d118f-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="d118f-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
