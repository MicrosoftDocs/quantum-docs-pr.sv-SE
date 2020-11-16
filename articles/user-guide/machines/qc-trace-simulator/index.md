---
title: Spårningssimulator för kvantdator – Quantum Development Kit
description: Lär dig att använda Microsofts spårningssimulator för kvantdatorer som felsöker klassisk kod och beräknar resurskraven för ett Q#-program.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 2e2d9f8494d8709fba34123793cecce4011b609a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690840"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="ab4ed-103">Spårningssimulator för kvantdator i Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="ab4ed-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="ab4ed-104">QDK-klassen <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> kör ett kvantprogram utan att egentligen simulera tillståndet för en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="ab4ed-105">Det innebär att kvantspårningssimulatorn kan köra kvantprogram som använder tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="ab4ed-106">Det är användbart av två viktiga orsaker:</span><span class="sxs-lookup"><span data-stu-id="ab4ed-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="ab4ed-107">Vid felsökning av klassisk kod som ingår i ett kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="ab4ed-108">Vid beräkning av vilka resurser som krävs för att köra en specifik instans av ett kvantprogram på en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="ab4ed-109">Faktum är att [resursberäknaren](xref:microsoft.quantum.machines.resources-estimator), som ger en mer begränsad uppsättning mätvärden, bygger på spårningssimulatorn.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="ab4ed-110">Anropa kvantspårningssimulatorn</span><span class="sxs-lookup"><span data-stu-id="ab4ed-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="ab4ed-111">Du kan använda kvantspårningssimulatorn till att köra valfri Q#-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="ab4ed-112">Precis som med andra måldatorer skapar du först en instans av klassen `QCTraceSimulator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="ab4ed-113">Observera att i motsats till `QuantumSimulator`-klassen implementerar `QCTraceSimulator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="ab4ed-114">Ange sannolikheten för mätresultatet</span><span class="sxs-lookup"><span data-stu-id="ab4ed-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="ab4ed-115">Eftersom kvantspårningssimulatorn inte simulerar det faktiska kvanttillståndet, kan den inte beräkna sannolikheten för mätresultatet i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="ab4ed-116">Om en åtgärd inkluderar mätningar måste du därför uttryckligen ange dessa sannolikheter med hjälp av <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>-åtgärden från namnområdet <xref:Microsoft.Quantum.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation from the <xref:Microsoft.Quantum.Diagnostics> namespace.</span></span> <span data-ttu-id="ab4ed-117">Följande exempel illustrerar detta:</span><span class="sxs-lookup"><span data-stu-id="ab4ed-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="ab4ed-118">När kvantspårningssimulatorn påträffar `AssertMeasurementProbability` kommer den registrera att mätning av `PauliZ` i `source` och `q` bör visa ett resultat på `Zero`, med sannolikheten **0,5** .</span><span class="sxs-lookup"><span data-stu-id="ab4ed-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5** .</span></span> <span data-ttu-id="ab4ed-119">När `M`-åtgärden körs senare hittar den de registrerade värdena i resultatets sannolikhet och `M` returnerar `Zero` eller `One`, med sannolikheten **0,5** .</span><span class="sxs-lookup"><span data-stu-id="ab4ed-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5** .</span></span> <span data-ttu-id="ab4ed-120">När samma kod körs i en simulator som håller koll på kvanttillståndet, kontrollerar simulatorn att de angivna sannolikheterna i `AssertMeasurementProbability` är korrekta.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="ab4ed-121">Observera att om det finns minst en mätningsåtgärd som inte är kommenterad med `AssertMeasurementProbability`, utlöser simulatorn ett [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="ab4ed-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="ab4ed-122">Verktyg för kvantspårningssimulator</span><span class="sxs-lookup"><span data-stu-id="ab4ed-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="ab4ed-123">QDK:n innehåller fem verktyg som du kan använda med kvantspårningssimulatorn för att hitta buggar i dina program och utföra beräkningar av kvantprogramresurser:</span><span class="sxs-lookup"><span data-stu-id="ab4ed-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="ab4ed-124">Verktyg</span><span class="sxs-lookup"><span data-stu-id="ab4ed-124">Tool</span></span> | <span data-ttu-id="ab4ed-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ab4ed-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="ab4ed-126">Kontroll av distinkta indata</span><span class="sxs-lookup"><span data-stu-id="ab4ed-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="ab4ed-127">Söker efter potentiella konflikter med delade kvantbitar</span><span class="sxs-lookup"><span data-stu-id="ab4ed-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="ab4ed-128">Kontroll av användning av upphävda kvantbitar</span><span class="sxs-lookup"><span data-stu-id="ab4ed-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="ab4ed-129">Kontrollerar om programmet tillämpar en åtgärd på en kvantbit som redan har släppts</span><span class="sxs-lookup"><span data-stu-id="ab4ed-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="ab4ed-130">Räknare för primitiva åtgärder</span><span class="sxs-lookup"><span data-stu-id="ab4ed-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="ab4ed-131">Räknar det antal primitiver som används av varje åtgärd som anropas i ett kvantprogram</span><span class="sxs-lookup"><span data-stu-id="ab4ed-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="ab4ed-132">Djupräknare</span><span class="sxs-lookup"><span data-stu-id="ab4ed-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="ab4ed-133">Samlar in antal som representerar de nedre gränserna för djupet i varje åtgärd som anropas i ett kvantprogram</span><span class="sxs-lookup"><span data-stu-id="ab4ed-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="ab4ed-134">Breddräknare</span><span class="sxs-lookup"><span data-stu-id="ab4ed-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="ab4ed-135">Räknar antalet allokerade och lånade kvantbitar för varje åtgärd i ett kvantprogram</span><span class="sxs-lookup"><span data-stu-id="ab4ed-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="ab4ed-136">Vart och ett av dessa verktyg aktiveras genom att ställa in lämpliga flaggor i `QCTraceSimulatorConfiguration` och sedan skicka konfigurationen till `QCTraceSimulator`-deklarationen.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="ab4ed-137">Information om hur du använder de olika verktygen finns i länkarna i föregående lista.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="ab4ed-138">Mer information om hur du konfigurerar `QCTraceSimulator` finns i [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ab4ed-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="ab4ed-139">QCTraceSimulator-metoder</span><span class="sxs-lookup"><span data-stu-id="ab4ed-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="ab4ed-140">`QCTraceSimulator` har flera inbyggda metoder för att hämta värdena för de mått som spåras under en kvantåtgärd.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="ab4ed-141">Exempel på [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric)- och [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv)-metoderna finns i artiklarna [Räknare för primitiva åtgärder](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Djupräknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) och [Breddräknare](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="ab4ed-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="ab4ed-142">Mer information om alla tillgängliga metoder finns i [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i Q# API-referensen.</span><span class="sxs-lookup"><span data-stu-id="ab4ed-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ab4ed-143">Se även</span><span class="sxs-lookup"><span data-stu-id="ab4ed-143">See also</span></span>

- [<span data-ttu-id="ab4ed-144">Kvantresursberäknare</span><span class="sxs-lookup"><span data-stu-id="ab4ed-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="ab4ed-145">Toffoli-kvantsimulator</span><span class="sxs-lookup"><span data-stu-id="ab4ed-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="ab4ed-146">Kvantsimulator med fullständigt tillstånd</span><span class="sxs-lookup"><span data-stu-id="ab4ed-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 