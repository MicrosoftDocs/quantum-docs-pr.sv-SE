---
title: Spårningssimulator för kvantdator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820444"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="1e04b-103">Spårningssimulator för kvantdator</span><span class="sxs-lookup"><span data-stu-id="1e04b-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="1e04b-104">Microsofts spårningssimulator för kvantdatorer kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="1e04b-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="1e04b-105">Det innebär att spårningssimulatorn kan köra kvantprogram som använder tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="1e04b-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="1e04b-106">Det är användbart av två viktiga orsaker:</span><span class="sxs-lookup"><span data-stu-id="1e04b-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="1e04b-107">Vid felsökning av klassisk kod som ingår i ett kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="1e04b-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="1e04b-108">Vid beräkning av vilka resurser som krävs för att köra en specifik instans av ett kvantprogram på en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="1e04b-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="1e04b-109">Spårningssimulatorn måste erhålla ytterligare information från användaren när mätningarna ska utföras.</span><span class="sxs-lookup"><span data-stu-id="1e04b-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="1e04b-110">Mer information om detta finns i avsnittet [Ange sannolikheten för mätresultatet](#providing-the-probability-of-measurement-outcomes).</span><span class="sxs-lookup"><span data-stu-id="1e04b-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="1e04b-111">Ange sannolikheten för mätresultatet</span><span class="sxs-lookup"><span data-stu-id="1e04b-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="1e04b-112">Det finns två typer av mått som syns i kvantalgoritmer.</span><span class="sxs-lookup"><span data-stu-id="1e04b-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="1e04b-113">Den första typen används när användaren vanligtvis känner till sannolikheten för resultatet.</span><span class="sxs-lookup"><span data-stu-id="1e04b-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="1e04b-114">I detta fall kan användaren skriva <xref:microsoft.quantum.intrinsic.assertprob> från namnområdet <xref:microsoft.quantum.intrinsic> för att visa att kunskapen finns.</span><span class="sxs-lookup"><span data-stu-id="1e04b-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="1e04b-115">Följande exempel illustrerar detta:</span><span class="sxs-lookup"><span data-stu-id="1e04b-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="1e04b-116">När spårningssimulatorn kör `AssertProb` kommer den registrera att mätning av `PauliZ` i `source` och `q` bör få ett resultat på `Zero` med sannolikheten 0,5.</span><span class="sxs-lookup"><span data-stu-id="1e04b-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="1e04b-117">När simulatorn senare kör `M` kommer den att hitta de registrerade värdena för resultatets sannolikhet och `M` returnerar `Zero` eller `One` med sannolikheten 0,5.</span><span class="sxs-lookup"><span data-stu-id="1e04b-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="1e04b-118">När samma kod körs på en simulator som håller koll på kvanttillståndet, kontrollerar simulatorn att de angivna sannolikheterna i `AssertProb` är korrekta.</span><span class="sxs-lookup"><span data-stu-id="1e04b-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="1e04b-119">Köra ditt program med spårningssimulatorn för kvantdatorer</span><span class="sxs-lookup"><span data-stu-id="1e04b-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="1e04b-120">Spårningssimulatorn för kvantdatorer kan betraktas som en annan måldator.</span><span class="sxs-lookup"><span data-stu-id="1e04b-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="1e04b-121">C#-drivrutinen för att använda den liknar den som finns för andra kvantsimulatorer:</span><span class="sxs-lookup"><span data-stu-id="1e04b-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="1e04b-122">Observera att om det finns minst en mätning som inte är kommenterad med `AssertProb`, kommer simulatorn att utlösa `UnconstrainedMeasurementException` från namnområdet `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="1e04b-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="1e04b-123">Mer information finns i API-dokumentationen om [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).</span><span class="sxs-lookup"><span data-stu-id="1e04b-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="1e04b-124">Förutom att köra kvantprogram levereras spårningssimulatorn med fem komponenter som identifierar buggar i program och utför uppskattningar av kvantprogramresurser:</span><span class="sxs-lookup"><span data-stu-id="1e04b-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="1e04b-125">Kontroll av distinkta indata</span><span class="sxs-lookup"><span data-stu-id="1e04b-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="1e04b-126">Upphävd användningskontroll för kvantbitar</span><span class="sxs-lookup"><span data-stu-id="1e04b-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="1e04b-127">Räknare för primitiva åtgärder</span><span class="sxs-lookup"><span data-stu-id="1e04b-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="1e04b-128">Räknare för kretsdjup</span><span class="sxs-lookup"><span data-stu-id="1e04b-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="1e04b-129">Räknare för kretsbredd</span><span class="sxs-lookup"><span data-stu-id="1e04b-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="1e04b-130">Var och en av dessa komponenter kan aktiveras genom att lämpliga flaggor anges i `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="1e04b-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="1e04b-131">Mer information om hur du använder de olika komponenterna finns i tillhörande referensfiler.</span><span class="sxs-lookup"><span data-stu-id="1e04b-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="1e04b-132">Mer information finns i API-dokumentationen om [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1e04b-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e04b-133">Se även</span><span class="sxs-lookup"><span data-stu-id="1e04b-133">See also</span></span>
<span data-ttu-id="1e04b-134">C#-referens till [spårningssimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) för kvantdator</span><span class="sxs-lookup"><span data-stu-id="1e04b-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

