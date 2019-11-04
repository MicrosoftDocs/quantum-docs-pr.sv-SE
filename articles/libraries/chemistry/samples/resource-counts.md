---
title: Hämtar resurs antal | Microsoft Docs
description: Hämtar dokument för resurs antal
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: f9311c1987ced4336c4e98bdb984fbee009e9acc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442459"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="d3d19-103">Få resursantal</span><span class="sxs-lookup"><span data-stu-id="d3d19-103">Obtaining resource counts</span></span>

<span data-ttu-id="d3d19-104">Kostnaden för att simulera $n $ qubits på klassiska datorer skalas exponentiellt med $n $.</span><span class="sxs-lookup"><span data-stu-id="d3d19-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="d3d19-105">Detta begränsar storleken på en Quantum kemi-simulering som vi kan utföra med hela tillstånds simulatorn.</span><span class="sxs-lookup"><span data-stu-id="d3d19-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="d3d19-106">För stora instanser av kemi kan vi ändå få värdefull information.</span><span class="sxs-lookup"><span data-stu-id="d3d19-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="d3d19-107">Här kan vi se hur resurs kostnader, till exempel antalet T-grindar eller CNOT-grindar, för att simulera kemi kan erhållas på ett automatiserat sätt med hjälp av [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="d3d19-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="d3d19-108">Sådan information informerar oss om att quantum-datorer kan vara tillräckligt stora för att köra dessa Quantum kemi-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="d3d19-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="d3d19-109">En referens finns i det tillhandahållna `GetGateCount` exemplet.</span><span class="sxs-lookup"><span data-stu-id="d3d19-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="d3d19-110">Låt oss anta att vi redan har en `FermionHamiltonian` instans, t. ex. inläst från Broombridge-schemat enligt beskrivningen i exemplet [inläsnings-från-fil](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="d3d19-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="d3d19-111">Syntaxen för att få resurs uppskattningar är nästan identiska för att köra algoritmen i full-State-simulatorn.</span><span class="sxs-lookup"><span data-stu-id="d3d19-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="d3d19-112">Vi väljer bara en annan måldator.</span><span class="sxs-lookup"><span data-stu-id="d3d19-112">We simply choose a different target machine.</span></span> <span data-ttu-id="d3d19-113">För resurs uppskattningar räcker det att utvärdera kostnaden för ett enda Trotter-steg eller en Quantum-åtgärd som skapats av Qubitization-tekniken.</span><span class="sxs-lookup"><span data-stu-id="d3d19-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="d3d19-114">Standard för att anropa dessa algoritmer är följande.</span><span class="sxs-lookup"><span data-stu-id="d3d19-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="d3d19-115">Nu konfigurerar vi spårnings simulatorn för att spåra de resurser vi är intresserade av.</span><span class="sxs-lookup"><span data-stu-id="d3d19-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="d3d19-116">I det här fallet räknar vi primitiva Quantum-åtgärder genom att ange `usePrimitiveOperationsCounter` flagga till `true`.</span><span class="sxs-lookup"><span data-stu-id="d3d19-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="d3d19-117">Ett tekniskt informations `throwOnUnconstraintMeasurement` är inställt på `false` för att undvika undantag i fall där Q #-koden inte är korrekt försäkrad om sannolikheten för Mät resultat, om sådana utförs.</span><span class="sxs-lookup"><span data-stu-id="d3d19-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="d3d19-118">Nu kör vi Quantum-algoritmen från driv rutins programmet på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="d3d19-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```