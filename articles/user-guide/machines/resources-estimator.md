---
title: Uppskattningar av Quantum Resources-Quantum Development Kit
description: Lär dig mer om Microsoft QDKs resurs uppskattning, som beräknar de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1892431c3e332385a5bcefa357eb64a9fac3f381
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992249"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="63e76-103">Uppskatta QDK-resurser (Quantum Development Kit)</span><span class="sxs-lookup"><span data-stu-id="63e76-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="63e76-104">Som namnet antyder `ResourcesEstimator` beräknar klassen de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="63e76-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="63e76-105">Detta åstadkommer detta genom att köra åtgärden Quantum utan att faktiskt simulera status för en Quantum-dator. av den anledningen beräknar den resurser för Q# åtgärder som använder tusentals qubits, förutsatt att den klassiska delen av koden körs på rimlig tid.</span><span class="sxs-lookup"><span data-stu-id="63e76-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="63e76-106">Resurs uppräkningen är byggd ovanpå [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), som ger en mer omfattande uppsättning mått och verktyg som hjälper dig att felsöka Q# program.</span><span class="sxs-lookup"><span data-stu-id="63e76-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="63e76-107">Anropar och kör resurs uppskattningen</span><span class="sxs-lookup"><span data-stu-id="63e76-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="63e76-108">Du kan använda resurs uppskattningen för att köra alla Q# åtgärder.</span><span class="sxs-lookup"><span data-stu-id="63e76-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="63e76-109">Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="63e76-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="63e76-110">Anropar resurs uppskattningen från C #</span><span class="sxs-lookup"><span data-stu-id="63e76-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="63e76-111">Precis som med andra måldatorer skapar du först en instans av klassen `ResourceEstimator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="63e76-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="63e76-112">Observera att i motsats till `QuantumSimulator`-klassen implementerar `ResourceEstimator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="63e76-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="63e76-113">Som exemplet visar `ResourcesEstimator` tillhandahåller `ToTSV()` metoden, som genererar en tabell med Tabbavgränsade värden (TSV).</span><span class="sxs-lookup"><span data-stu-id="63e76-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="63e76-114">Du kan spara tabellen till en fil eller Visa den i konsolen för analys.</span><span class="sxs-lookup"><span data-stu-id="63e76-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="63e76-115">Följande är ett exempel på utdata från föregående program:</span><span class="sxs-lookup"><span data-stu-id="63e76-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="63e76-116">En `ResourcesEstimator` instans återställer inte sina beräkningar vid varje körning.</span><span class="sxs-lookup"><span data-stu-id="63e76-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="63e76-117">Om du använder samma instans för att köra en annan åtgärd sammanställs de nya resultaten med de befintliga resultaten.</span><span class="sxs-lookup"><span data-stu-id="63e76-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="63e76-118">Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.</span><span class="sxs-lookup"><span data-stu-id="63e76-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="63e76-119">Anropar resurs uppskattningen från python</span><span class="sxs-lookup"><span data-stu-id="63e76-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="63e76-120">Använd metoden [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q# åtgärden:</span><span class="sxs-lookup"><span data-stu-id="63e76-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="63e76-121">Anropar resurs uppskattningen från kommando raden</span><span class="sxs-lookup"><span data-stu-id="63e76-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="63e76-122">När du kör ett Q# program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange `ResourcesEstimator` mål datorn.</span><span class="sxs-lookup"><span data-stu-id="63e76-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="63e76-123">Följande kommando kör ett program med hjälp av resurs uppskattningen:</span><span class="sxs-lookup"><span data-stu-id="63e76-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="63e76-124">Anropar resurs uppskattningen från Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="63e76-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="63e76-125">Använd Q# kommandot% unmagic kommandot [%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="63e76-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="63e76-126">Hämta beräknade data program mässigt</span><span class="sxs-lookup"><span data-stu-id="63e76-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="63e76-127">Förutom en TSV-tabell kan du program mässigt hämta de beräknade resurserna under körning via `Data` egenskapen för resurs uppskattningen.</span><span class="sxs-lookup"><span data-stu-id="63e76-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="63e76-128">`Data`Egenskapen ger en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerat av måttets namn.</span><span class="sxs-lookup"><span data-stu-id="63e76-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="63e76-129">Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` - `T` och- `CNOT` åtgärder som används av en Q# åtgärd:</span><span class="sxs-lookup"><span data-stu-id="63e76-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="63e76-130">Rapporterade mått</span><span class="sxs-lookup"><span data-stu-id="63e76-130">Metrics Reported</span></span>

<span data-ttu-id="63e76-131">Resurs uppskattningen spårar följande mått:</span><span class="sxs-lookup"><span data-stu-id="63e76-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="63e76-132">Mått</span><span class="sxs-lookup"><span data-stu-id="63e76-132">Metric</span></span>|<span data-ttu-id="63e76-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="63e76-133">Description</span></span>|
|----|----|
|<span data-ttu-id="63e76-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="63e76-134">__CNOT__</span></span>    |<span data-ttu-id="63e76-135">Antalet körningar av `CNOT` åtgärder (även kallat kontrollerade Pauli X-åtgärder).</span><span class="sxs-lookup"><span data-stu-id="63e76-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="63e76-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="63e76-136">__QubitClifford__</span></span> |<span data-ttu-id="63e76-137">Antalet körningar av alla enskilda qubit Clifford-och Pauli-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="63e76-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="63e76-138">__Mått__</span><span class="sxs-lookup"><span data-stu-id="63e76-138">__Measure__</span></span>    |<span data-ttu-id="63e76-139">Antalet körningar av alla mätningar.</span><span class="sxs-lookup"><span data-stu-id="63e76-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="63e76-140">__R__</span><span class="sxs-lookup"><span data-stu-id="63e76-140">__R__</span></span>    |<span data-ttu-id="63e76-141">Antalet körningar av en enskild-qubit rotations, exklusive `T` , Clifford och Pauli åtgärder.</span><span class="sxs-lookup"><span data-stu-id="63e76-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="63e76-142">__T__</span><span class="sxs-lookup"><span data-stu-id="63e76-142">__T__</span></span>    |<span data-ttu-id="63e76-143">Antalet körningar av `T` åtgärder och deras konjugat, inklusive `T` åtgärderna, T_x = H. T. H och T_y = hy. T. hy.</span><span class="sxs-lookup"><span data-stu-id="63e76-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="63e76-144">__Djuplodande__</span><span class="sxs-lookup"><span data-stu-id="63e76-144">__Depth__</span></span>|<span data-ttu-id="63e76-145">Den nedre gränserna för djupet i Quantum-kretsen som körs av Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="63e76-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="63e76-146">Djup måttet räknar som standard bara `T` grindar.</span><span class="sxs-lookup"><span data-stu-id="63e76-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="63e76-147">Mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="63e76-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="63e76-148">__Bredd__</span><span class="sxs-lookup"><span data-stu-id="63e76-148">__Width__</span></span>    |<span data-ttu-id="63e76-149">Den nedre gränsen för maximalt antal allokerade qubits under körningen av Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="63e76-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="63e76-150">Det kanske inte går att uppnå både __djup__ och __Bredd__ nedre gränser samtidigt.</span><span class="sxs-lookup"><span data-stu-id="63e76-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="63e76-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="63e76-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="63e76-152">Det maximala antalet qubits som lånas i Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="63e76-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="63e76-153">Ange sannolikheten för mätresultatet</span><span class="sxs-lookup"><span data-stu-id="63e76-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="63e76-154">Du kan använda <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> från <xref:microsoft.quantum.diagnostics> namn området för att ge information om den förväntade sannolikheten för en mätnings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="63e76-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="63e76-155">Mer information finns i [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="63e76-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="63e76-156">Se även</span><span class="sxs-lookup"><span data-stu-id="63e76-156">See also</span></span>

- [<span data-ttu-id="63e76-157">Quantum trace Simulator</span><span class="sxs-lookup"><span data-stu-id="63e76-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="63e76-158">Toffoli-kvantsimulator</span><span class="sxs-lookup"><span data-stu-id="63e76-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="63e76-159">Kvantsimulator med fullständigt tillstånd</span><span class="sxs-lookup"><span data-stu-id="63e76-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 