---
title: Uppskattningar av Quantum Resources-Quantum Development Kit
description: Lär dig mer om Microsoft QDKs resurs uppskattning, som beräknar de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57f6602effd25fff353a8fee7f27acc529ce82af
ms.sourcegitcommit: c3c892ef35eae6926d0c4339d9d26bfd8be77e9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2020
ms.locfileid: "96318498"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="bc647-103">Uppskatta QDK-resurser (Quantum Development Kit)</span><span class="sxs-lookup"><span data-stu-id="bc647-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="bc647-104">Som namnet antyder `ResourcesEstimator` beräknar klassen de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="bc647-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="bc647-105">Detta uppnår detta genom att köra åtgärden Quantum utan att faktiskt simulera en Quantum-dators tillstånd. av den anledningen beräknar den resurser för Q# åtgärder som använder tusentals qubits, förutsatt att den klassiska delen av koden körs på rimlig tid.</span><span class="sxs-lookup"><span data-stu-id="bc647-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="bc647-106">Resurs uppräkningen är byggd ovanpå [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), som ger en mer omfattande uppsättning mått och verktyg som hjälper dig att felsöka Q# program.</span><span class="sxs-lookup"><span data-stu-id="bc647-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="bc647-107">Anropar och kör resurs uppskattningen</span><span class="sxs-lookup"><span data-stu-id="bc647-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="bc647-108">Du kan använda resurs uppskattningen för att köra alla Q# åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc647-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="bc647-109">Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="bc647-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="bc647-110">Anropar resurs uppskattningen från C #</span><span class="sxs-lookup"><span data-stu-id="bc647-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="bc647-111">Precis som med andra måldatorer skapar du först en instans av klassen `ResourceEstimator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="bc647-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="bc647-112">Observera att i motsats till `QuantumSimulator`-klassen implementerar `ResourceEstimator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="bc647-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="bc647-113">Som exemplet visar `ResourcesEstimator` tillhandahåller `ToTSV()` metoden, som genererar en tabell med Tabbavgränsade värden (TSV).</span><span class="sxs-lookup"><span data-stu-id="bc647-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="bc647-114">Du kan spara tabellen till en fil eller Visa den i konsolen för analys.</span><span class="sxs-lookup"><span data-stu-id="bc647-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="bc647-115">Följande är ett exempel på utdata från föregående program:</span><span class="sxs-lookup"><span data-stu-id="bc647-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="bc647-116">En `ResourcesEstimator` instans återställer inte sina beräkningar vid varje körning.</span><span class="sxs-lookup"><span data-stu-id="bc647-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="bc647-117">Om du använder samma instans för att köra en annan åtgärd sammanställs de nya resultaten med de befintliga resultaten.</span><span class="sxs-lookup"><span data-stu-id="bc647-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="bc647-118">Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.</span><span class="sxs-lookup"><span data-stu-id="bc647-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="bc647-119">Anropar resurs uppskattningen från python</span><span class="sxs-lookup"><span data-stu-id="bc647-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="bc647-120">Använd metoden [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q# åtgärden:</span><span class="sxs-lookup"><span data-stu-id="bc647-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="bc647-121">Anropar resurs uppskattningen från kommando raden</span><span class="sxs-lookup"><span data-stu-id="bc647-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="bc647-122">När du kör ett Q# program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange `ResourcesEstimator` mål datorn.</span><span class="sxs-lookup"><span data-stu-id="bc647-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="bc647-123">Följande kommando kör ett program med hjälp av resurs uppskattningen:</span><span class="sxs-lookup"><span data-stu-id="bc647-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="bc647-124">Anropar resurs uppskattningen från Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="bc647-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="bc647-125">Använd Q# kommandot% unmagic kommandot [%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bc647-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="bc647-126">Hämta beräknade data program mässigt</span><span class="sxs-lookup"><span data-stu-id="bc647-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="bc647-127">Förutom en TSV-tabell kan du program mässigt hämta de beräknade resurserna under körning via `Data` egenskapen för resurs uppskattningen.</span><span class="sxs-lookup"><span data-stu-id="bc647-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="bc647-128">`Data`Egenskapen ger en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerat av måttets namn.</span><span class="sxs-lookup"><span data-stu-id="bc647-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="bc647-129">Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` - `T` och- `CNOT` åtgärder som används av en Q# åtgärd:</span><span class="sxs-lookup"><span data-stu-id="bc647-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="bc647-130">Rapporterade mått</span><span class="sxs-lookup"><span data-stu-id="bc647-130">Metrics Reported</span></span>

<span data-ttu-id="bc647-131">Resurs uppskattningen spårar följande mått:</span><span class="sxs-lookup"><span data-stu-id="bc647-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="bc647-132">Metric</span><span class="sxs-lookup"><span data-stu-id="bc647-132">Metric</span></span>|<span data-ttu-id="bc647-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bc647-133">Description</span></span>|
|----|----|
|<span data-ttu-id="bc647-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="bc647-134">__CNOT__</span></span>    |<span data-ttu-id="bc647-135">Antalet körningar av `CNOT` åtgärder (även kallat kontrollerade Pauli X-åtgärder).</span><span class="sxs-lookup"><span data-stu-id="bc647-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="bc647-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="bc647-136">__QubitClifford__</span></span> |<span data-ttu-id="bc647-137">Antalet körningar av alla enskilda qubit Clifford-och Pauli-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc647-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="bc647-138">__Mått__</span><span class="sxs-lookup"><span data-stu-id="bc647-138">__Measure__</span></span>    |<span data-ttu-id="bc647-139">Antalet körningar av alla mätningar.</span><span class="sxs-lookup"><span data-stu-id="bc647-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="bc647-140">__R__</span><span class="sxs-lookup"><span data-stu-id="bc647-140">__R__</span></span>    |<span data-ttu-id="bc647-141">Antalet körningar av en enskild-qubit rotations, exklusive `T` , Clifford och Pauli åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc647-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="bc647-142">__T__</span><span class="sxs-lookup"><span data-stu-id="bc647-142">__T__</span></span>    |<span data-ttu-id="bc647-143">Antalet körningar av `T` åtgärder och deras konjugat, inklusive `T` åtgärderna, T_x = H. T. H och T_y = hy. T. hy.</span><span class="sxs-lookup"><span data-stu-id="bc647-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="bc647-144">__Djuplodande__</span><span class="sxs-lookup"><span data-stu-id="bc647-144">__Depth__</span></span>|<span data-ttu-id="bc647-145">Djupet i Quantum-kretsen som körs av Q# åtgärden (se [nedan](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="bc647-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="bc647-146">Djup måttet räknar som standard bara `T` grindar.</span><span class="sxs-lookup"><span data-stu-id="bc647-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="bc647-147">Mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="bc647-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="bc647-148">__LED__</span><span class="sxs-lookup"><span data-stu-id="bc647-148">__Width__</span></span>|<span data-ttu-id="bc647-149">Bredden på den Quantum-krets som körs av Q# åtgärden (se [nedan](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="bc647-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="bc647-150">Djup måttet räknar som standard bara `T` grindar.</span><span class="sxs-lookup"><span data-stu-id="bc647-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="bc647-151">Mer information finns i [räknare för bredd](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="bc647-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="bc647-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="bc647-152">__QubitCount__</span></span>    |<span data-ttu-id="bc647-153">Den nedre gränsen för maximalt antal allokerade qubits under körningen av Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bc647-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="bc647-154">Det här måttet kanske inte är kompatibelt med __djupet__ (se nedan).</span><span class="sxs-lookup"><span data-stu-id="bc647-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="bc647-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="bc647-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="bc647-156">Det maximala antalet qubits som lånas i Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bc647-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="bc647-157">Djup, bredd och QubitCount</span><span class="sxs-lookup"><span data-stu-id="bc647-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="bc647-158">Rapporterade djup och bredd beräkningar är kompatibla med varandra.</span><span class="sxs-lookup"><span data-stu-id="bc647-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="bc647-159">(Tidigare båda talen var möjliga, men olika kretsar krävs för djup och bredd.) För närvarande kan båda måtten i det här paret uppnås med samma krets på samma tillfälle.</span><span class="sxs-lookup"><span data-stu-id="bc647-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="bc647-160">Följande mått rapporteras:</span><span class="sxs-lookup"><span data-stu-id="bc647-160">The following metrics are reported:</span></span>

<span data-ttu-id="bc647-161">__Djup:__ För rot åtgärds tiden det tar att utföra den antar vissa grind tider.</span><span class="sxs-lookup"><span data-stu-id="bc647-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="bc647-162">För åtgärder som kallas eller efterföljande åtgärds tids skillnad mellan den senaste qubit tillgänglighets tiden i början och slutet av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bc647-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="bc647-163">__Bredd:__ För rot åtgärden – antalet qubits som faktiskt använts för att köra det (och anropet till den).</span><span class="sxs-lookup"><span data-stu-id="bc647-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="bc647-164">För åtgärder som kallas eller efterföljande åtgärder – hur många fler qubits som användes utöver qubits som redan användes i början av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bc647-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="bc647-165">Observera att återanvända qubits inte bidrar till det här numret.</span><span class="sxs-lookup"><span data-stu-id="bc647-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="bc647-166">T. ex. om några qubits har släppts innan en åtgärd A startar och alla qubit som krävs av den här åtgärden (och åtgärder som anropas från A) var uppfyllda genom att återanvända tidigare versions qubits, så rapporteras bredden A till 0.</span><span class="sxs-lookup"><span data-stu-id="bc647-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="bc647-167">Lånade qubits bidrar inte till bredden.</span><span class="sxs-lookup"><span data-stu-id="bc647-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="bc647-168">__QubitCount:__ För rot åtgärden – minsta antal qubits som skulle räcka för att utföra den här åtgärden (och åtgärder som anropas från den).</span><span class="sxs-lookup"><span data-stu-id="bc647-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="bc647-169">För åtgärder som anropas eller efterföljande åtgärder – minsta antal qubits som skulle räcka för att utföra den här åtgärden separat.</span><span class="sxs-lookup"><span data-stu-id="bc647-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="bc647-170">Det här talet inkluderar inte inqubits.</span><span class="sxs-lookup"><span data-stu-id="bc647-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="bc647-171">Det innefattar lånade qubits.</span><span class="sxs-lookup"><span data-stu-id="bc647-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="bc647-172">Två drifts lägen stöds.</span><span class="sxs-lookup"><span data-stu-id="bc647-172">Two modes of operation are supported.</span></span> <span data-ttu-id="bc647-173">Läge väljs genom att ställa in QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="bc647-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="bc647-174">__OptimizeDepth = True:__ QubitManager rekommenderas inte från qubit åter användning och allokerar nya qubit varje gång den begär en qubit.</span><span class="sxs-lookup"><span data-stu-id="bc647-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="bc647-175">För rot åtgärdens __djup__ blir det minsta djupet (nedre gräns).</span><span class="sxs-lookup"><span data-stu-id="bc647-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="bc647-176">Kompatibel __Bredd__ rapporteras för det här djupet (båda kan uppnås samtidigt).</span><span class="sxs-lookup"><span data-stu-id="bc647-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="bc647-177">Observera att den här bredden sannolikt inte är optimalt för detta djup.</span><span class="sxs-lookup"><span data-stu-id="bc647-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="bc647-178">__QubitCount__ kan vara lägre än bredden för rot åtgärden eftersom den tar återanvända.</span><span class="sxs-lookup"><span data-stu-id="bc647-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="bc647-179">__OptimizeDepth = falskt:__ QubitManager uppmanas att återanvända qubits och återanvända de utgivna qubits innan du allokerar nya.</span><span class="sxs-lookup"><span data-stu-id="bc647-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="bc647-180">__Bredden__ för rot åtgärden blir den minimala bredden (nedre gränser).</span><span class="sxs-lookup"><span data-stu-id="bc647-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="bc647-181">Ett kompatibelt __djup__ rapporteras som kan uppnås.</span><span class="sxs-lookup"><span data-stu-id="bc647-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="bc647-182">__QubitCount__ kommer att vara samma som __bredden__ för rot åtgärden förutsatt att ingen lånar.</span><span class="sxs-lookup"><span data-stu-id="bc647-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="bc647-183">Ange sannolikheten för mätresultatet</span><span class="sxs-lookup"><span data-stu-id="bc647-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="bc647-184">Du kan använda <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> från <xref:Microsoft.Quantum.Diagnostics> namn området för att ge information om den förväntade sannolikheten för en mätnings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="bc647-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="bc647-185">Mer information finns i [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="bc647-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="bc647-186">Se även</span><span class="sxs-lookup"><span data-stu-id="bc647-186">See also</span></span>

- [<span data-ttu-id="bc647-187">Quantum trace Simulator</span><span class="sxs-lookup"><span data-stu-id="bc647-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="bc647-188">Toffoli-kvantsimulator</span><span class="sxs-lookup"><span data-stu-id="bc647-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="bc647-189">Kvantsimulator med fullständigt tillstånd</span><span class="sxs-lookup"><span data-stu-id="bc647-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
