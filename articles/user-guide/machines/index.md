---
title: Kvantsimulatorer och Q#-program
description: Beskriver de kvantsimulatorer som är tillgängliga som måldatorer för Q#-program.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: f40c63eed60379aa46a0cd9cfdd7d8de8c22c079
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771304"
---
# <a name="quantum-simulators"></a><span data-ttu-id="b6e22-103">Kvantsimulatorer</span><span class="sxs-lookup"><span data-stu-id="b6e22-103">Quantum simulators</span></span>

<span data-ttu-id="b6e22-104">Kvantsimulatorer är program som körs på klassiska datorer och fungerar som *måldatorer* för Q#-program. Detta gör det möjligt att köra och testa kvantprogram i en miljö som kan förutsäga hur kvantbitar kommer att reagera på olika åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b6e22-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="b6e22-105">I den här artikeln beskrivs vilka kvantsimulatorer som ingår i Quantum Development Kit (QDK) och olika sätt att skicka Q#-program till kvantsimulatorer, till exempel via kommandoraden eller med hjälp av drivrutinskod som skrivs på ett klassiskt språk.</span><span class="sxs-lookup"><span data-stu-id="b6e22-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="b6e22-106">Kvantsimulatorer i Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b6e22-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="b6e22-107">Kvantsimulatorn ansvarar för att tillhandahålla implementeringar av kvantprimitiver för en algoritm.</span><span class="sxs-lookup"><span data-stu-id="b6e22-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="b6e22-108">Detta inkluderar primitiva åtgärder som t.ex. `H`, `CNOT` och `Measure`, samt hantering och spårning av kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="b6e22-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="b6e22-109">QDK innehåller olika klasser av kvantsimulatorer som representerar olika sätt att simulera samma kvantalgoritm.</span><span class="sxs-lookup"><span data-stu-id="b6e22-109">The QDK includes different classes of quantum simulators representing different ways of simulating the same quantum algorithm.</span></span> 


<span data-ttu-id="b6e22-110">Varje typ av kvantsimulator kan ge olika implementeringar av dessa primitiver.</span><span class="sxs-lookup"><span data-stu-id="b6e22-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="b6e22-111">Till exempel kör en [simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) kvantalgoritmen genom att helt simulera [kvanttillståndsvektorn](xref:microsoft.quantum.glossary#quantum-state), medan [spårningssimulatorn för kvantdatorer](xref:microsoft.quantum.machines.qc-trace-simulator.intro) inte bryr sig om det faktiska kvanttillståndet alls.</span><span class="sxs-lookup"><span data-stu-id="b6e22-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="b6e22-112">I stället spårar den grind-, kvantbits- och annan resursanvändning för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="b6e22-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="b6e22-113">Kvantdatorklasser</span><span class="sxs-lookup"><span data-stu-id="b6e22-113">Quantum machine classes</span></span>

<span data-ttu-id="b6e22-114">Framöver kommer QDK:n att kunna definiera ytterligare kvantdatorklasser som har stöd för andra typer av simulering och stöd för körning på kvantmaskinvara.</span><span class="sxs-lookup"><span data-stu-id="b6e22-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="b6e22-115">Om algoritmen tillåts vara konstant samtidigt som den underliggande datorimplementeringen varierar, blir det enkelt att testa och felsöka en algoritm i simuleringen. Den kan sedan köras på verklig maskinvara och man kan vara säker på att algoritmen inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="b6e22-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="b6e22-116">QDK:n innehåller flera kvantdatorklasser som definieras i namnområdet `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="b6e22-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="b6e22-117">Simulator</span><span class="sxs-lookup"><span data-stu-id="b6e22-117">Simulator</span></span> |<span data-ttu-id="b6e22-118">Klass</span><span class="sxs-lookup"><span data-stu-id="b6e22-118">Class</span></span>|<span data-ttu-id="b6e22-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b6e22-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="b6e22-120">Simulator med fullständigt tillstånd</span><span class="sxs-lookup"><span data-stu-id="b6e22-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="b6e22-121">Kör och felsöker kvantalgoritmer och är begränsad till cirka 30 kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="b6e22-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="b6e22-122">Enkel resursberäknare</span><span class="sxs-lookup"><span data-stu-id="b6e22-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="b6e22-123">Gör en analys på toppnivå av vilka resurser som krävs för att köra en kvantalgoritm och har stöd för tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="b6e22-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="b6e22-124">Spårningsbaserad resursberäknare</span><span class="sxs-lookup"><span data-stu-id="b6e22-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="b6e22-125">Kör avancerad analys av resursförbrukningen för algoritmens hela anropsgraf och har stöd för tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="b6e22-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="b6e22-126">Toffoli-simulator</span><span class="sxs-lookup"><span data-stu-id="b6e22-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="b6e22-127">Simulerar kvantalgoritmer som är begränsade till `X`, `CNOT` och multistyrda `X` kvantåtgärder och har stöd för miljontals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="b6e22-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="b6e22-128">Anropa kvantsimulatorn</span><span class="sxs-lookup"><span data-stu-id="b6e22-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="b6e22-129">I [Sätt att köra ett Q#-program på](xref:microsoft.quantum.guide.host-programs) visas tre sätt att skicka Q#-koden till kvantsimulatorn:</span><span class="sxs-lookup"><span data-stu-id="b6e22-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="b6e22-130">Använda kommandoraden</span><span class="sxs-lookup"><span data-stu-id="b6e22-130">Using the command line</span></span>
* <span data-ttu-id="b6e22-131">Använda ett Python-värdprogram</span><span class="sxs-lookup"><span data-stu-id="b6e22-131">Using a Python host program</span></span>
* <span data-ttu-id="b6e22-132">Använda ett C#-värdprogram</span><span class="sxs-lookup"><span data-stu-id="b6e22-132">Using a C# host program</span></span>

<span data-ttu-id="b6e22-133">Kvantdatorer är instanser av vanliga .NET-klasser, vilket innebär att de skapas genom att anropa sin konstruktor, precis som alla andra .NET-klasser.</span><span class="sxs-lookup"><span data-stu-id="b6e22-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="b6e22-134">Hur du gör detta beror på hur du kör Q#-programmet.</span><span class="sxs-lookup"><span data-stu-id="b6e22-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6e22-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b6e22-135">Next steps</span></span>

* <span data-ttu-id="b6e22-136">Mer information om hur du anropar måldatorer för Q#-program i olika miljöer finns i [Sätt att köra ett Q#-program på](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b6e22-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
