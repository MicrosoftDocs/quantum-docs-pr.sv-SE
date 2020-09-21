---
title: Räknare för primitiva åtgärder – Quantum Development Kit
description: Lär dig mer om räknaren för primitiva Microsoft-QDK, som använder Quantum trace Simulator för att spåra primitiva processer som används av åtgärder i ett Q# program.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8ee9ce25e680112e2f3c68d82ae9267c1b0fb355
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835986"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="a3686-103">Quantum trace Simulator: primitiva åtgärds räknare</span><span class="sxs-lookup"><span data-stu-id="a3686-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="a3686-104">Räknaren primitiv åtgärd är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="a3686-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a3686-105">Det räknar antalet primitiva processer som används av varje åtgärd som anropas i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="a3686-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="a3686-106">Alla <xref:microsoft.quantum.intrinsic> åtgärder uttrycks i form av en qubit rotation, T-åtgärder, qubit Clifford-åtgärder, CNOT-åtgärder och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="a3686-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="a3686-107">Räknaren för primitiva åtgärder sammanställer och samlar in statistik över alla kanter i åtgärdens [anrops diagram](https://en.wikipedia.org/wiki/Call_graph).</span><span class="sxs-lookup"><span data-stu-id="a3686-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="a3686-108">Anropar den primitiva åtgärds räknaren</span><span class="sxs-lookup"><span data-stu-id="a3686-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="a3686-109">Om du vill köra Quantum trace-simulatorn med den primitiva åtgärds räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ange `UsePrimitiveOperationsCounter` egenskapen till **True**och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="a3686-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="a3686-110">Använda den primitiva åtgärds räknaren i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="a3686-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="a3686-111">C#-exemplet som följer i det här avsnittet räknar hur många <xref:microsoft.quantum.intrinsic.t> åtgärder som krävs för att implementera <xref:microsoft.quantum.intrinsic.ccnot> åtgärden, baserat på följande Q# exempel kod:</span><span class="sxs-lookup"><span data-stu-id="a3686-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="a3686-112">`CCNOT`Använd följande C#-kod för att kontrol lera att kräver sju `T` åtgärder och som `ApplySampleWithCCNOT` Kör åtta `T` åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a3686-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="a3686-113">Den första delen av programmet körs `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="a3686-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="a3686-114">Den andra delen använder [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta antalet `T` åtgärder som körs av `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="a3686-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="a3686-115">När du anropar `GetMetric` med två typ parametrar returnerar den värdet för måttet som är kopplat till en specifik anrops diagram gräns.</span><span class="sxs-lookup"><span data-stu-id="a3686-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="a3686-116">I föregående exempel anropar programmet `Primitive.CCNOT` åtgärden i `ApplySampleWithCCNOT` och därför innehåller anrops diagrammet kanten `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="a3686-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="a3686-117">`CNOT`Lägg till följande rad för att hämta antalet åtgärder som används:</span><span class="sxs-lookup"><span data-stu-id="a3686-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="a3686-118">Slutligen kan du skriva ut all statistik som samlas in av räknaren primitiva åtgärder i CSV-format med hjälp av följande:</span><span class="sxs-lookup"><span data-stu-id="a3686-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="a3686-119">Se även</span><span class="sxs-lookup"><span data-stu-id="a3686-119">See also</span></span>

- <span data-ttu-id="a3686-120">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="a3686-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="a3686-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="a3686-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="a3686-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="a3686-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="a3686-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="a3686-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>