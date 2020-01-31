---
title: Räknare för primitiva åtgärder | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820427"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="6f230-103">Räknare för primitiva åtgärder</span><span class="sxs-lookup"><span data-stu-id="6f230-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="6f230-104">`Primitive Operations Counter` ingår i Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="6f230-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6f230-105">Det räknar antalet primitiva körningar som används av varje åtgärd som anropas i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="6f230-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="6f230-106">Alla åtgärder från `Microsoft.Quantum.Intrinsic` uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="6f230-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6f230-107">Insamlad statistik sammanställs över kanterna på diagrammet för Operations-anropet.</span><span class="sxs-lookup"><span data-stu-id="6f230-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="6f230-108">Nu räknar vi hur många `T` portar som behövs för att implementera `CCNOT`s åtgärden.</span><span class="sxs-lookup"><span data-stu-id="6f230-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="6f230-109">Använda primitiva åtgärds räknare i C# ett program</span><span class="sxs-lookup"><span data-stu-id="6f230-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="6f230-110">För att kontrol lera att `CCNOT` verkligen kräver 7 `T` portar och att `ApplySampleWithCCNOT` kör 8 `T` portar kan vi använda följande C# kod:</span><span class="sxs-lookup"><span data-stu-id="6f230-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="6f230-111">Den första delen av programmet körs `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="6f230-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="6f230-112">I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet T-portar som körs av `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="6f230-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="6f230-113">När `GetMetric` anropas med två typ parametrar returneras värdet för måttet som är kopplat till en specifik anrops kurva.</span><span class="sxs-lookup"><span data-stu-id="6f230-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="6f230-114">I vårt exempel åtgärds `Primitive.CCNOT` anropas i `ApplySampleWithCCNOT` och därför innehåller anrops diagrammet gränsen `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="6f230-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="6f230-115">Vi kan lägga till följande rad för att få antalet `CNOT` portar som används:</span><span class="sxs-lookup"><span data-stu-id="6f230-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="6f230-116">Slutligen kan vi använda följande för att mata ut all statistik som samlas in av grind räknaren i CSV-format:</span><span class="sxs-lookup"><span data-stu-id="6f230-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="6f230-117">Se också</span><span class="sxs-lookup"><span data-stu-id="6f230-117">See also</span></span> ##

- <span data-ttu-id="6f230-118">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="6f230-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
