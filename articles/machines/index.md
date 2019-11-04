---
title: Kvantsimulatorer och värdprogram | Microsoft Docs
description: Beskriver hur du använder kvantsimulatorer med ett klassiskt .NET-språk, vanligtvis antingen C# eller Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442228"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="59a09-103">Kvantsimulatorer och värdprogram</span><span class="sxs-lookup"><span data-stu-id="59a09-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="59a09-104">Detta får du lära dig</span><span class="sxs-lookup"><span data-stu-id="59a09-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="59a09-105">Hur kvantalgoritmer körs</span><span class="sxs-lookup"><span data-stu-id="59a09-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="59a09-106">Vilka kvantsimulatorer som ingår i den här versionen</span><span class="sxs-lookup"><span data-stu-id="59a09-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="59a09-107">Hur du skriver en C#-drivrutin för kvantalgoritmen</span><span class="sxs-lookup"><span data-stu-id="59a09-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="59a09-108">Körningsmodell för Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="59a09-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="59a09-109">I [Att skriva ett kvantprogram](xref:microsoft.quantum.write-program) körde vi vår kvantalgoritm genom att skicka ett `QuantumSimulator`-objekt till algoritmklassens `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="59a09-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="59a09-110">`QuantumSimulator`-klassen kör kvantalgoritmen genom att helt simulera kvanttillståndets vektor, vilket är perfekt när man vill köra och testa `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="59a09-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="59a09-111">I [Begreppsguide](xref:microsoft.quantum.concepts.intro) finns mer information om kvanttillståndsvektorer.</span><span class="sxs-lookup"><span data-stu-id="59a09-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="59a09-112">Andra måldatorer kan användas för att köra en kvantalgoritm.</span><span class="sxs-lookup"><span data-stu-id="59a09-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="59a09-113">Datorn ansvarar för att tillhandahålla implementeringar av kvantprimitiver för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="59a09-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="59a09-114">Detta inkluderar primitiva åtgärder som t. ex. H, CNOT och Measure, samt hantering och spårning av kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="59a09-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="59a09-115">Olika klasser i kvantdatorer representerar olika körningsmodeller för samma kvantalgoritm.</span><span class="sxs-lookup"><span data-stu-id="59a09-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="59a09-116">Varje typ av kvantdator kan ge olika implementeringar av dessa primitiver.</span><span class="sxs-lookup"><span data-stu-id="59a09-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="59a09-117">Till exempel utför spårningssimulatorn för kvantdatorn som ingår i utvecklingspaketet inte någon simulering alls.</span><span class="sxs-lookup"><span data-stu-id="59a09-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="59a09-118">I stället spårar den grind-, kvantbits- och annan resursanvändning för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="59a09-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="59a09-119">Kvantdatorer</span><span class="sxs-lookup"><span data-stu-id="59a09-119">Quantum Machines</span></span>

<span data-ttu-id="59a09-120">Senare definierar vi ytterligare kvantdatorklasser som har stöd för andra typer av simulering och stöd för körning på topologiska kvantdatorer.</span><span class="sxs-lookup"><span data-stu-id="59a09-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="59a09-121">Om algoritmen tillåts vara konstant samtidigt som den underliggande datorimplementeringen varierar, blir det enkelt att testa och felsöka en algoritm i simuleringen. Den kan sedan köras på verklig maskinvara och man kan vara säker på att algoritmen inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="59a09-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="59a09-122">Vad ingår i den här versionen?</span><span class="sxs-lookup"><span data-stu-id="59a09-122">What's Included in this Release</span></span>

<span data-ttu-id="59a09-123">Den här versionen av Quantum Developer Kit innehåller flera kvantdatorklasser.</span><span class="sxs-lookup"><span data-stu-id="59a09-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="59a09-124">Alla definieras i namnområdet `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="59a09-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="59a09-125">En [vektorsimulator för fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`-klassen.</span><span class="sxs-lookup"><span data-stu-id="59a09-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="59a09-126">En [enkel resursberäknare](xref:microsoft.quantum.machines.resources-estimator), `ResourcesEstimator`-klassen. Beräknaren gör en analys på toppnivå av vilka resurser som krävs för att köra en kvantalgoritm.</span><span class="sxs-lookup"><span data-stu-id="59a09-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="59a09-127">En [spårningsbaserad resursberäknare](xref:microsoft.quantum.machines.qc-trace-simulator.intro), `QCTraceSimulator`-klassen. Beräknaren möjliggör avancerad analys av resursförbrukningen för algoritmens hela anropsgraf.</span><span class="sxs-lookup"><span data-stu-id="59a09-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="59a09-128">En [Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator), `ToffoliSimulator`-klassen.</span><span class="sxs-lookup"><span data-stu-id="59a09-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="59a09-129">Skriva ett värdprogram</span><span class="sxs-lookup"><span data-stu-id="59a09-129">Writing a host application</span></span>

<span data-ttu-id="59a09-130">I [Att skriva ett kvantprogram](xref:microsoft.quantum.write-program) skrev vi en enkel C#-drivrutin för vår teleporteringsalgoritm.</span><span class="sxs-lookup"><span data-stu-id="59a09-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="59a09-131">En C#-drivrutin har fyra huvudsakliga syften:</span><span class="sxs-lookup"><span data-stu-id="59a09-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="59a09-132">Skapa måldatorn</span><span class="sxs-lookup"><span data-stu-id="59a09-132">Constructing the target machine</span></span>
* <span data-ttu-id="59a09-133">Beräkna eventuella argument som krävs för kvantalgoritmen</span><span class="sxs-lookup"><span data-stu-id="59a09-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="59a09-134">Köra kvantalgoritmen med simulatorn</span><span class="sxs-lookup"><span data-stu-id="59a09-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="59a09-135">Bearbeta resultatet av åtgärden</span><span class="sxs-lookup"><span data-stu-id="59a09-135">Processing the result of the operation</span></span>

<span data-ttu-id="59a09-136">Här diskuterar vi varje steg mer ingående.</span><span class="sxs-lookup"><span data-stu-id="59a09-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="59a09-137">Skapa måldatorn</span><span class="sxs-lookup"><span data-stu-id="59a09-137">Constructing the Target Machine</span></span>

<span data-ttu-id="59a09-138">Kvantdatorer är instanser av vanliga .NET-klasser, vilket innebär att de skapas genom att anropa sin konstruktor, precis som alla andra .NET-klasser.</span><span class="sxs-lookup"><span data-stu-id="59a09-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="59a09-139">Vissa simulatorer, inklusive `QuantumSimulator`, implementerar .NET <xref:System.IDisposable?displayProperty=nameWithType>-gränssnittet och ska omslutas i en C#`using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="59a09-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="59a09-140">Beräkna argument för algoritmen</span><span class="sxs-lookup"><span data-stu-id="59a09-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="59a09-141">I vårt `Teleport`-exempel beräknade vi några relativt artificiella argument som ska skickas till vår kvantalgoritm.</span><span class="sxs-lookup"><span data-stu-id="59a09-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="59a09-142">Det är dock vanligare att det finns viktiga data som krävs av kvantalgoritmen, och det är enklast att tillhandahålla den från den klassiska drivrutinen.</span><span class="sxs-lookup"><span data-stu-id="59a09-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="59a09-143">Vid kemiska simuleringar kräver till exempel kvantalgoritmen en stor tabell med interaktionsintegraler för molekylorbitaler.</span><span class="sxs-lookup"><span data-stu-id="59a09-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="59a09-144">De läses vanligtvis in från en fil som tillhandahålls när algoritmen körs.</span><span class="sxs-lookup"><span data-stu-id="59a09-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="59a09-145">Eftersom Q# inte har någon metod för att komma åt filsystemet, samlas dessa datatyper in bäst av den klassiska drivrutinen och skickas sedan till kvantalgoritmens `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="59a09-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="59a09-146">Ett annat fall där den klassiska drivrutinen spelar en nyckelroll är i variationsmetoder.</span><span class="sxs-lookup"><span data-stu-id="59a09-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="59a09-147">I den här algoritmklassen förbereds ett kvanttillstånd som baseras på vissa klassiska parametrar. Detta tillstånd används sedan för att beräkna specifika intressanta värden.</span><span class="sxs-lookup"><span data-stu-id="59a09-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="59a09-148">Parametrarna justeras baserat på algoritmtypen hill climbing eller maskininlärning, varefter kvantalgoritmen körs igen.</span><span class="sxs-lookup"><span data-stu-id="59a09-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="59a09-149">Vid sådana algoritmer implementeras hill climbing-algoritmen bäst som en helt klassisk funktion som anropas av den klassiska drivrutinen. Resultatet av hill climbing-algoritmen skickas sedan till nästa körning av kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="59a09-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="59a09-150">Köra kvantalgoritmen</span><span class="sxs-lookup"><span data-stu-id="59a09-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="59a09-151">Den här delen är i allmänhet rätt okomplicerad.</span><span class="sxs-lookup"><span data-stu-id="59a09-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="59a09-152">Varje Q#-åtgärd kompileras till en klass som tillhandahåller en statisk `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="59a09-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="59a09-153">Argumenten till den här metoden kommer från den utplattade argumenttuppeln för själva åtgärden, plus ett ytterligare första argument som är simulatorn som ska köras.</span><span class="sxs-lookup"><span data-stu-id="59a09-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="59a09-154">För en åtgärd som förväntar sig den namngivna tuppeln av typen `(a: String, (b: Double, c: Double))`, är dess utplattade motsvarighet av typen `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="59a09-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="59a09-155">Det finns vissa saker att tänka på när argument skickas till en `Run`-metod:</span><span class="sxs-lookup"><span data-stu-id="59a09-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="59a09-156">Matriser måste vara omslutna i ett `Microsoft.Quantum.Simulation.Core.QArray<T>`-objekt.</span><span class="sxs-lookup"><span data-stu-id="59a09-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="59a09-157">En `QArray`-klass har en konstruktor som kan hantera alla sorterade samlingar (`IEnumerable<T>`) med lämpliga objekt.</span><span class="sxs-lookup"><span data-stu-id="59a09-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="59a09-158">Den tomma tuppeln, `()` i Q#, representeras av `QVoid.Instance` i C#.</span><span class="sxs-lookup"><span data-stu-id="59a09-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="59a09-159">Tupplar som inte är tomma representeras som `ValueTuple`-instanser i .NET.</span><span class="sxs-lookup"><span data-stu-id="59a09-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="59a09-160">Q#-användardefinierade typer skickas som bastypen.</span><span class="sxs-lookup"><span data-stu-id="59a09-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="59a09-161">Om du vill skicka en åtgärd eller en funktion till en `Run`-metod, måste du hämta en instans av åtgärdens eller funktionens klass med hjälp av simulatorns `Get<>`-metod.</span><span class="sxs-lookup"><span data-stu-id="59a09-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="59a09-162">Bearbeta resultat</span><span class="sxs-lookup"><span data-stu-id="59a09-162">Processing the Results</span></span>

<span data-ttu-id="59a09-163">Resultatet av kvantalgoritmen returneras från `Run`-metoden.</span><span class="sxs-lookup"><span data-stu-id="59a09-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="59a09-164">`Run`-metoden körs asynkront och returnerar därför en instans av <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="59a09-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="59a09-165">Det finns flera sätt att hämta det faktiska åtgärdsresultatet på.</span><span class="sxs-lookup"><span data-stu-id="59a09-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="59a09-166">Det enklaste är att använda `Task`:s [`Result`-egenskap](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span><span class="sxs-lookup"><span data-stu-id="59a09-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="59a09-167">Men andra tekniker, som att använda [`Wait`-metoden](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) eller [`await`-nyckelord](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) i C# fungerar också.</span><span class="sxs-lookup"><span data-stu-id="59a09-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="59a09-168">Precis som i argument visas Q#-tupplar som `ValueTuple`-instanser och Q#-matriser visas som `QArray`-instanser.</span><span class="sxs-lookup"><span data-stu-id="59a09-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="59a09-169">Användardefinierade typer skickas som bastyper.</span><span class="sxs-lookup"><span data-stu-id="59a09-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="59a09-170">Den tomma tuppeln, `()`, returneras som en instans av klassen `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="59a09-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="59a09-171">Många kvantalgoritmer kräver avsevärd efterbearbetning för att kunna härleda användbara svar.</span><span class="sxs-lookup"><span data-stu-id="59a09-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="59a09-172">Till exempel är kvantdelen av Shors algoritm bara början av en beräkning som hittar faktorerna i ett tal.</span><span class="sxs-lookup"><span data-stu-id="59a09-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="59a09-173">I de flesta fall är det enklast att göra denna typ av efterbearbetning i den klassiska drivrutinen.</span><span class="sxs-lookup"><span data-stu-id="59a09-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="59a09-174">Det är bara den klassiska drivrutinen som kan rapportera resultat till användaren eller skriva dem till disk.</span><span class="sxs-lookup"><span data-stu-id="59a09-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="59a09-175">Den klassiska drivrutinen har åtkomst till analysbibliotek och andra matematiska funktioner som inte visas i Q#.</span><span class="sxs-lookup"><span data-stu-id="59a09-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="59a09-176">Fel</span><span class="sxs-lookup"><span data-stu-id="59a09-176">Failures</span></span>

<span data-ttu-id="59a09-177">När Q# `fail`-instruktionen nås under körningen av en åtgärd, utlöses ett `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="59a09-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="59a09-178">Eftersom `System.Task` har använts i `Run`-metoden utlöses ett undantagsfel som orsakas av att en `fail`-instruktion kommer att omslutas i ett `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="59a09-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="59a09-179">För att hitta den faktiska orsaken till det här felet måste du iterera i `AggregateException` 
`InnerExceptions`, till exempel:</span><span class="sxs-lookup"><span data-stu-id="59a09-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="59a09-180">Andra klassiska språk</span><span class="sxs-lookup"><span data-stu-id="59a09-180">Other Classical Languages</span></span>

<span data-ttu-id="59a09-181">Även om de exempel som vi har visat är i C#, F# och Python, har Quantum Development Kit också stöd för att skriva klassiska värdprogram på andra språk.</span><span class="sxs-lookup"><span data-stu-id="59a09-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="59a09-182">Om du till exempel vill skriva ett värdprogram i Visual Basic [går det utmärkt](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="59a09-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
