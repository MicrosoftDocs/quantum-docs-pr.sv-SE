---
title: Sätt att köra ett Q# program
description: Översikt över olika sätt att köra Q# program. Från kommando raden, Q# Jupyter antecknings böcker och klassiska värd program i python eller ett .net-språk.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869740"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="b91be-104">Sätt att köra ett Q# program</span><span class="sxs-lookup"><span data-stu-id="b91be-104">Ways to run a Q# program</span></span>

<span data-ttu-id="b91be-105">Ett av de största fördelarna med Quantum Development Kit är dess flexibilitet i plattforms-och utvecklings miljöer.</span><span class="sxs-lookup"><span data-stu-id="b91be-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="b91be-106">Det innebär dock också att nya Q# användare kan upptäcka att de många alternativen finns i [installations guiden](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b91be-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="b91be-107">På den här sidan förklarar vi vad som händer när ett Q# program körs och jämför de olika sätt som användarna kan göra.</span><span class="sxs-lookup"><span data-stu-id="b91be-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="b91be-108">En primär distinktion är att Q# du kan köra:</span><span class="sxs-lookup"><span data-stu-id="b91be-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="b91be-109">som ett fristående program, där Q# är det enda språk som ingår och programmet anropas direkt.</span><span class="sxs-lookup"><span data-stu-id="b91be-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="b91be-110">Två metoder är faktiskt i den här kategorin:</span><span class="sxs-lookup"><span data-stu-id="b91be-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="b91be-111">kommando rads gränssnittet</span><span class="sxs-lookup"><span data-stu-id="b91be-111">the command line interface</span></span>
  - <span data-ttu-id="b91be-112">Q#Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="b91be-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="b91be-113">med ett ytterligare *värd program*, skrivet i python eller ett .net-språk (t. ex. C# eller F #), som sedan anropar programmet och kan bearbeta returnerade resultat ytterligare.</span><span class="sxs-lookup"><span data-stu-id="b91be-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="b91be-114">För att bäst förstå de här processerna och deras skillnader, Överväg vi ett enkelt Q# program och jämför hur det kan utföras.</span><span class="sxs-lookup"><span data-stu-id="b91be-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="b91be-115">Basic- Q# program</span><span class="sxs-lookup"><span data-stu-id="b91be-115">Basic Q# program</span></span>

<span data-ttu-id="b91be-116">Ett grundläggande Quantum-program kan bestå av att förbereda en qubit i en lika stor position av tillstånden $ \ket {0} $ och $ \ket {1} $, mäta den och returnera resultatet, vilket kommer att slumpmässigt vara ett av dessa två tillstånd med samma sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="b91be-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="b91be-117">Den här processen är den som är kärnan i snabb starten av [Quantum slump tals Generator](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="b91be-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="b91be-118">I Q# kan detta utföras med följande kod:</span><span class="sxs-lookup"><span data-stu-id="b91be-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="b91be-119">Den här koden kan dock inte utföras av Q# .</span><span class="sxs-lookup"><span data-stu-id="b91be-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="b91be-120">För att göra det måste du skapa en [Åtgärds](xref:microsoft.quantum.guide.basics#q-operations-and-functions)brödtext, som sedan körs när du anropar---antingen direkt eller av en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b91be-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="b91be-121">Därför kan du skriva en åtgärd i följande format:</span><span class="sxs-lookup"><span data-stu-id="b91be-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="b91be-122">Du har definierat en åtgärd, `MeasureSuperposition` som inte tar några indata och returnerar ett värde av typen [result](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="b91be-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="b91be-123">Även om exemplen på den här sidan bara består av Q# *åtgärder*, kommer alla koncept som vi diskuterar att diskutera är lika med Q# *funktioner*, och därför kan vi se dem gemensamt som *callables*.</span><span class="sxs-lookup"><span data-stu-id="b91be-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="b91be-124">Skillnaderna beskrivs i [ Q# grunderna: åtgärder och funktioner](xref:microsoft.quantum.guide.basics#q-operations-and-functions), och mer information om hur du definierar dem finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b91be-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="b91be-125">Det går att anropa i en Q# fil</span><span class="sxs-lookup"><span data-stu-id="b91be-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="b91be-126">Anropet är exakt vad som anropas och körs av Q# .</span><span class="sxs-lookup"><span data-stu-id="b91be-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="b91be-127">Det krävs dock några fler tillägg för att omfatta en fullständig `*.qs` Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="b91be-128">Alla Q# typer och callables (både de som du definierar och de är inbyggda i språket) definieras i *namn områden*som ger varje fullständigt namn som sedan kan refereras.</span><span class="sxs-lookup"><span data-stu-id="b91be-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="b91be-129">Till exempel finns- [`H`](xref:microsoft.quantum.intrinsic.h) och- [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) åtgärderna i [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namn områdena och (ingår i [ Q# standard biblioteken](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="b91be-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="b91be-130">Därför kan de alltid anropas via sina *fullständiga* namn `Microsoft.Quantum.Intrinsic.H(<qubit>)` och `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , men alltid göra detta skulle leda till mycket rörig kod.</span><span class="sxs-lookup"><span data-stu-id="b91be-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="b91be-131">I stället kan `open` callables refereras till med en mer koncis kort text som vi har gjort i åtgärds texten ovan.</span><span class="sxs-lookup"><span data-stu-id="b91be-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="b91be-132">Den fullständiga Q# filen som innehåller vår åtgärd skulle därför bestå av att definiera vår egen namnrymd, öppna namn områdena för de callables som vår åtgärd använder och sedan vår åtgärd:</span><span class="sxs-lookup"><span data-stu-id="b91be-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="b91be-133">Namn områden kan också vara *aliasade* när de öppnas, vilket kan vara användbart om anrops bara/typnamn i två namn områden står i konflikt.</span><span class="sxs-lookup"><span data-stu-id="b91be-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="b91be-134">Vi kan till exempel använda `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ovanstående, och sedan anropa `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="b91be-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="b91be-135">Ett undantag till allt detta är [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namn området, som alltid öppnas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b91be-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="b91be-136">Därför kan callables som [`Length`](xref:microsoft.quantum.core.length) alltid användas direkt.</span><span class="sxs-lookup"><span data-stu-id="b91be-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="b91be-137">Körning på mål datorer</span><span class="sxs-lookup"><span data-stu-id="b91be-137">Execution on target machines</span></span>

<span data-ttu-id="b91be-138">Nu är den allmänna körnings modellen för ett Q# program avmarkerad.</span><span class="sxs-lookup"><span data-stu-id="b91be-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="b91be-139">För det första har det speciella anropet att utföras ha åtkomst till alla andra callables och typer som definierats i samma namnrymd.</span><span class="sxs-lookup"><span data-stu-id="b91be-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="b91be-140">De kommer även åt dem från alla [ Q# bibliotek](xref:microsoft.quantum.libraries), men de måste refereras antingen via deras fullständiga namn eller genom användning av `open` instruktioner som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="b91be-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="b91be-141">Själva anropet körs sedan på en *[måldator](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="b91be-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="b91be-142">Sådana mål datorer kan vara faktiska Quantum-maskinvara eller flera simulatorer som är tillgängliga som en del av QDK.</span><span class="sxs-lookup"><span data-stu-id="b91be-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="b91be-143">För våra behov är den mest användbara mål datorn en instans av [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` som beräknar programmets beteende som om den kördes på en brus fri dator som är en brus fri.</span><span class="sxs-lookup"><span data-stu-id="b91be-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="b91be-144">Hittills har vi beskrivit vad som händer när en speciell Q# anrop utförs.</span><span class="sxs-lookup"><span data-stu-id="b91be-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="b91be-145">Oavsett om används Q# i ett fristående program eller med ett värd program, är den här generella processen mer eller mindre---, och därför är QDK flexibiliteten.</span><span class="sxs-lookup"><span data-stu-id="b91be-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="b91be-146">Skillnaderna mellan olika sätt att anropa i Quantum Development Kit visas därför i *hur* det kan anropas Q# för att utföras och på vilket sätt resultaten returneras.</span><span class="sxs-lookup"><span data-stu-id="b91be-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="b91be-147">Mer specifikt kretsar skiljer sig runt</span><span class="sxs-lookup"><span data-stu-id="b91be-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="b91be-148">indikerar vilket anrop som ska Q# utföras,</span><span class="sxs-lookup"><span data-stu-id="b91be-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="b91be-149">Hur potentiella anrops bara argument tillhandahålls,</span><span class="sxs-lookup"><span data-stu-id="b91be-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="b91be-150">Ange den måldator där du vill köra den och</span><span class="sxs-lookup"><span data-stu-id="b91be-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="b91be-151">hur resultat returneras.</span><span class="sxs-lookup"><span data-stu-id="b91be-151">how any results are returned.</span></span>

<span data-ttu-id="b91be-152">Först diskuterar vi hur detta görs med det Q# fristående programmet från kommando raden och fortsätter sedan med att använda python-och C#-värd program.</span><span class="sxs-lookup"><span data-stu-id="b91be-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="b91be-153">Vi reserverar det fristående programmet för Q# Jupyter Notebooks för sista, eftersom till skillnad från de tre första, är den primära funktionen inte en lokal Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="b91be-154">Även om vi inte illustrerar det i de här exemplen, är en gemensam lösning mellan körnings metoderna att alla meddelanden som skrivs ut inifrån Q# programmet (av [`Message`](xref:microsoft.quantum.intrinsic.message) eller till [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) exempel) alltid skrivs ut till respektive konsol.</span><span class="sxs-lookup"><span data-stu-id="b91be-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-line"></a><span data-ttu-id="b91be-155">Q#från kommando raden</span><span class="sxs-lookup"><span data-stu-id="b91be-155">Q# from the command line</span></span>
<span data-ttu-id="b91be-156">Ett av de enklaste sätten att komma igång med att skriva Q# program är att undvika att behöva oroa dig för separata filer och ett andra språk helt och hållet.</span><span class="sxs-lookup"><span data-stu-id="b91be-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="b91be-157">Med hjälp av Visual Studio Code eller Visual Studio med QDK-tillägget kan du använda ett sömlöst arbets flöde där vi kör Q# callables från endast en enda Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="b91be-158">För detta kommer vi i slut ändan att starta program körningen genom att ange</span><span class="sxs-lookup"><span data-stu-id="b91be-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b91be-159">på kommando raden.</span><span class="sxs-lookup"><span data-stu-id="b91be-159">in the command line.</span></span>
<span data-ttu-id="b91be-160">Det enklaste arbets flödet är när terminalens katalog plats är samma som Q# filen, som enkelt kan hanteras tillsammans Q# med fil redigering genom att använda den integrerade terminalen i vs Code, till exempel.</span><span class="sxs-lookup"><span data-stu-id="b91be-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="b91be-161">[ `dotnet run` Kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) godkänner dock flera alternativ, och programmet kan också köras från en annan plats genom att bara ange `--project <PATH>` platsen för Q# filen.</span><span class="sxs-lookup"><span data-stu-id="b91be-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="b91be-162">Lägg till Start punkt till Q# fil</span><span class="sxs-lookup"><span data-stu-id="b91be-162">Add entry point to Q# file</span></span>

<span data-ttu-id="b91be-163">De flesta Q# filer kommer att innehålla mer än ett anrops bara, så det är naturligt att låta kompileraren ta reda på *vilket* anrop som kan utföras när vi tillhandahåller `dotnet run` kommandot.</span><span class="sxs-lookup"><span data-stu-id="b91be-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="b91be-164">Detta görs med en enkel ändring i Q# själva filen:</span><span class="sxs-lookup"><span data-stu-id="b91be-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="b91be-165">Lägg till en rad med `@EntryPoint()` direkt föregående anrop.</span><span class="sxs-lookup"><span data-stu-id="b91be-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="b91be-166">Vår fil ovan skulle därför bli</span><span class="sxs-lookup"><span data-stu-id="b91be-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="b91be-167">Nu kommer ett anrop `dotnet run` från kommando raden att `MeasureSuperposition` köras och det returnerade värdet skrivs sedan direkt till terminalen.</span><span class="sxs-lookup"><span data-stu-id="b91be-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="b91be-168">Så visas antingen `One` eller `Zero` skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="b91be-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="b91be-169">Observera att det inte spelar någon roll om du har angett fler callables under den, så `MeasureSuperposition` körs endast.</span><span class="sxs-lookup"><span data-stu-id="b91be-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="b91be-170">Dessutom är det inget problem om ditt anrop bara innehåller [dokumentations kommentarer](xref:microsoft.quantum.guide.filestructure#documentation-comments) före dess deklaration, så `@EntryPoint()` kan attributet placeras ovanför dem.</span><span class="sxs-lookup"><span data-stu-id="b91be-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="b91be-171">Anrops bara argument</span><span class="sxs-lookup"><span data-stu-id="b91be-171">Callable arguments</span></span>

<span data-ttu-id="b91be-172">Hittills har vi bara sett en åtgärd som inte kräver några indata.</span><span class="sxs-lookup"><span data-stu-id="b91be-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="b91be-173">Anta att vi ville utföra en liknande åtgärd, men på flera qubits---det antal som tillhandahålls som ett argument.</span><span class="sxs-lookup"><span data-stu-id="b91be-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="b91be-174">Sådan åtgärd kan skrivas som</span><span class="sxs-lookup"><span data-stu-id="b91be-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="b91be-175">där det returnerade värdet är en matris av mått resultatet.</span><span class="sxs-lookup"><span data-stu-id="b91be-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="b91be-176">Observera att [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) och [`ForEach`](xref:microsoft.quantum.arrays.foreach) är i [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namn områdena och som kräver ytterligare `open` instruktioner för varje.</span><span class="sxs-lookup"><span data-stu-id="b91be-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="b91be-177">Om vi flyttar `@EntryPoint()` attributet till före den här nya åtgärden (Observera att det bara kan finnas en sådan rad i en fil), försöker köra det med bara `dotnet run` resulterar i ett fel meddelande som anger vilka ytterligare kommando rads alternativ som krävs och hur du uttrycker dem.</span><span class="sxs-lookup"><span data-stu-id="b91be-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="b91be-178">Det allmänna formatet för kommando raden är faktiskt `dotnet run [options]` och det finns argument som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="b91be-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="b91be-179">I det här fallet saknas argumentet `n` , och det visar att vi behöver tillhandahålla alternativet `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b91be-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="b91be-180">För att köra `MeasureSuperpositionArray` för `n=4` qubits använder vi därför</span><span class="sxs-lookup"><span data-stu-id="b91be-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="b91be-181">ge utdata som liknar</span><span class="sxs-lookup"><span data-stu-id="b91be-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="b91be-182">Den här kursen utökar till flera argument.</span><span class="sxs-lookup"><span data-stu-id="b91be-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="b91be-183">Argument namn som definieras i `camelCase` har ändrats något av kompilatorn som ska godkännas som Q# indata.</span><span class="sxs-lookup"><span data-stu-id="b91be-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="b91be-184">Om till exempel i stället för `n` , vi använde namnet `numQubits` ovan, skulle den här indatan tillhandahållas på kommando raden via `--num-qubits 4` i stället för `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="b91be-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="b91be-185">Fel meddelandet innehåller också andra alternativ som kan användas, inklusive hur du ändrar mål datorn.</span><span class="sxs-lookup"><span data-stu-id="b91be-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="b91be-186">Olika mål datorer</span><span class="sxs-lookup"><span data-stu-id="b91be-186">Different target machines</span></span>

<span data-ttu-id="b91be-187">Eftersom utmatningarna från våra åtgärder hittills har varit det förväntade resultatet av sin åtgärd på verkliga qubits, är det uppenbart att standard mål datorn från kommando raden är quauntum-simulatorn med full status `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="b91be-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="b91be-188">Vi kan dock instruera callables att köras på en speciell måldator med alternativet `--simulator` (eller kort `-s` ).</span><span class="sxs-lookup"><span data-stu-id="b91be-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="b91be-189">Vi kan till exempel köra den på [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="b91be-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="b91be-190">De utskrivna utdata är sedan</span><span class="sxs-lookup"><span data-stu-id="b91be-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="b91be-191">Mer information om vad dessa mått anger finns i [resurs uppskattningen: statistik rapporteras](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="b91be-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="b91be-192">Sammanfattning av kommando rads körning</span><span class="sxs-lookup"><span data-stu-id="b91be-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="b91be-193">Icke- Q# `dotnet run` alternativ</span><span class="sxs-lookup"><span data-stu-id="b91be-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="b91be-194">Som vi nämnde ovan med `--project` alternativet godkänner [ `dotnet run` kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) också alternativ som inte är relaterade till de Q# anrops bara argumenten.</span><span class="sxs-lookup"><span data-stu-id="b91be-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="b91be-195">Om du tillhandahåller båda typerna av alternativ `dotnet` måste de-/regionsspecifika alternativen anges först, följt av en avgränsare `--` och sedan de Q# -/regionsspecifika alternativen.</span><span class="sxs-lookup"><span data-stu-id="b91be-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="b91be-196">Till exempel kan specifiying en sökväg tillsammans med en nummer qubits för åtgärden ovan köras via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b91be-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="b91be-197">Q#med värd program</span><span class="sxs-lookup"><span data-stu-id="b91be-197">Q# with host programs</span></span>

<span data-ttu-id="b91be-198">Med vår Q# fil i handen är ett alternativ för att anropa en åtgärd eller funktion direkt från kommando raden att använda ett *värd program* i ett annat klassiskt språk.</span><span class="sxs-lookup"><span data-stu-id="b91be-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="b91be-199">Mer specifikt kan detta göras med antingen python eller ett .NET-språk, till exempel C# eller F # (för det kortfattat vi bara detaljerat C# här).</span><span class="sxs-lookup"><span data-stu-id="b91be-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="b91be-200">Lite mer konfiguration krävs för att aktivera samverkan, men informationen finns i [installations guiderna](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b91be-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b91be-201">I en kortfattat så Jenkins innehåller situationen nu en värd program fil (t. ex. `*.py` eller `*.cs` ) på samma plats som vår Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="b91be-202">Det är nu *värd* programmet som körs och i samband med körningen kan det anropa vissa Q# åtgärder och funktioner från Q# filen.</span><span class="sxs-lookup"><span data-stu-id="b91be-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="b91be-203">Kärnornas kärna baseras på Q# kompilatorn som gör innehållet i Q# filen tillgängligt för värd programmet så att de kan anropas.</span><span class="sxs-lookup"><span data-stu-id="b91be-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="b91be-204">En av de främsta fördelarna med att använda ett värd program är att de klassiska data som returneras av Q# programmet kan bearbetas ytterligare på värd språket.</span><span class="sxs-lookup"><span data-stu-id="b91be-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="b91be-205">Detta kan bestå av en avancerad data bearbetning (t. ex. något som inte kan utföras internt i Q# ) och sedan anropa ytterligare Q# åtgärder baserat på dessa resultat eller något så enkelt som att rita Q# resultatet.</span><span class="sxs-lookup"><span data-stu-id="b91be-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="b91be-206">Det allmänna schemat visas här och vi diskuterar de olika implementeringarna för python och C# nedan.</span><span class="sxs-lookup"><span data-stu-id="b91be-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="b91be-207">Ett exempel som använder ett F # Host-program finns i [.net-samverkan exempel](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b91be-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="b91be-208">`@EntryPoint()`Attributet som används för Q# kommando rads program kan inte användas med värd program.</span><span class="sxs-lookup"><span data-stu-id="b91be-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="b91be-209">Ett fel genereras om det finns i den Q# fil som anropas av en värd.</span><span class="sxs-lookup"><span data-stu-id="b91be-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="b91be-210">Om du vill arbeta med olika värd program krävs inga ändringar i en `*.qs` Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="b91be-211">Följande värd program implementerar allt arbete med samma Q# fil:</span><span class="sxs-lookup"><span data-stu-id="b91be-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="b91be-212">Välj den flik som motsvarar värd språket i intresse.</span><span class="sxs-lookup"><span data-stu-id="b91be-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="b91be-213">Python</span><span class="sxs-lookup"><span data-stu-id="b91be-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="b91be-214">Ett python-värdprogram skapas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b91be-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="b91be-215">Importera `qsharp` modulen som registrerar modulens inläsare för Q# interoperabilitet.</span><span class="sxs-lookup"><span data-stu-id="b91be-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b91be-216">Detta gör Q# att namn områden kan visas som python-moduler, från vilka vi kan importera Q# callables.</span><span class="sxs-lookup"><span data-stu-id="b91be-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="b91be-217">Observera att det tekniskt sett inte är Q# callablest som importeras, men hellre python-stub-stub som tillåter att de anropar dem.</span><span class="sxs-lookup"><span data-stu-id="b91be-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="b91be-218">De fungerar sedan som objekt i python-klasser, där vi använder metoder för att ange de mål datorer som åtgärden ska skickas till för körning.</span><span class="sxs-lookup"><span data-stu-id="b91be-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="b91be-219">Importera de Q# callables som vi kommer att anropa direkt---i det här fallet `MeasureSuperposition` och `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="b91be-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="b91be-220">När `qsharp` modulen har importer ATS kan du också importera callables direkt från Q# biblioteks namn områdena.</span><span class="sxs-lookup"><span data-stu-id="b91be-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="b91be-221">Bland alla andra python-koder kan du nu anropa dessa callables på specifika mål datorer och tilldela deras returer till variabler (om de returnerar ett värde) för att användas.</span><span class="sxs-lookup"><span data-stu-id="b91be-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="b91be-222">Ange mål datorer</span><span class="sxs-lookup"><span data-stu-id="b91be-222">Specifying target machines</span></span>
<span data-ttu-id="b91be-223">Att anropa en åtgärd som ska köras på en särskild måldator görs via olika python-metoder för det importerade objektet.</span><span class="sxs-lookup"><span data-stu-id="b91be-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="b91be-224">Till exempel `.simulate(<args>)` använder, för `QuantumSimulator` att köra åtgärden, men gör det `.estimate_resources(<args>)` på `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="b91be-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="b91be-225">Skicka indata till Q\#</span><span class="sxs-lookup"><span data-stu-id="b91be-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="b91be-226">Argument för anrop kan anges Q# i form av ett nyckelord, där nyckelordet är argument namnet i den Q# anropade definitionen.</span><span class="sxs-lookup"><span data-stu-id="b91be-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="b91be-227">Det vill säga är `MeasureSuperpositionArray.simulate(n=4)` giltigt, vilket `MeasureSuperpositionArray.simulate(4)` skulle resultera i ett fel.</span><span class="sxs-lookup"><span data-stu-id="b91be-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="b91be-228">Det innebär att python-värd programmet</span><span class="sxs-lookup"><span data-stu-id="b91be-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="b91be-229">resulterar i utdata som följande:</span><span class="sxs-lookup"><span data-stu-id="b91be-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="b91be-230">C#</span><span class="sxs-lookup"><span data-stu-id="b91be-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b91be-231">Ett C#-värdprogram har flera komponenter och fungerar mycket nära vissa komponenter i QDK, till exempel simulatorer, som är inbyggda i C#.</span><span class="sxs-lookup"><span data-stu-id="b91be-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="b91be-232">Q#Kompilatorn fungerar här genom att generera ett likvärdigt namngivet C#-namnområde från Q# namn området i vår Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="b91be-233">Den genererar ytterligare en motsvarande namngiven C#-klass för var och en av de Q# callables eller typer som definieras däri.</span><span class="sxs-lookup"><span data-stu-id="b91be-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="b91be-234">Först gör vi några klasser som används i vårt värd program `using` som är tillgängliga med instruktioner, som är ungefär analagousa till `open` uttrycken i vår Q# fil:</span><span class="sxs-lookup"><span data-stu-id="b91be-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="b91be-235">Härnäst deklarerar vi vårt C#-namnrum, några andra bitar och delar (se hela kod blocket nedan) och sedan en klassisk programmering som vi vill ha (t. ex. beräknings argument för Q# callables).</span><span class="sxs-lookup"><span data-stu-id="b91be-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="b91be-236">Den senare är inte nödvändig i vårt fall, men ett exempel på en sådan användning finns i [exempel på .net-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b91be-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="b91be-237">Måldatorer</span><span class="sxs-lookup"><span data-stu-id="b91be-237">Target machines</span></span>

<span data-ttu-id="b91be-238">Kom tillbaka till Q# , vi måste skapa en instans av den mål dator som vi kommer att köra våra åtgärder på.</span><span class="sxs-lookup"><span data-stu-id="b91be-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="b91be-239">Att använda andra mål datorer är lika enkelt som att instansiera en annan, även om sättet att göra så och bearbetning av returerna kan vara något annorlunda.</span><span class="sxs-lookup"><span data-stu-id="b91be-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="b91be-240">För det kortfattat går vi till [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) för tillfället och inkluderar [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [nedan](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="b91be-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="b91be-241">Varje C#-klass som genereras från Q# åtgärder har en `Run` metod, vars första argument måste vara mål datorns instans.</span><span class="sxs-lookup"><span data-stu-id="b91be-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="b91be-242">Så att du kan köra `MeasureSuperposition` på `QuantumSimulator` , vi använder `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="b91be-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="b91be-243">De returnerade resultaten kan sedan tilldelas variabler i C#:</span><span class="sxs-lookup"><span data-stu-id="b91be-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="b91be-244">`Run`Metoden körs asynkront eftersom det är fallet för verkligt Quantum-maskinvara, och därför `await` blockerar nyckelordet ytterligare körning tills aktiviteten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="b91be-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="b91be-245">Om Q# anropet inte har några returer (t. ex. har retur typen `Unit` ) kan körningen fortfarande utföras på samma sätt utan att tilldela den till en variabel.</span><span class="sxs-lookup"><span data-stu-id="b91be-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="b91be-246">I så fall skulle hela raden helt enkelt bestå av</span><span class="sxs-lookup"><span data-stu-id="b91be-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="b91be-247">Argument</span><span class="sxs-lookup"><span data-stu-id="b91be-247">Arguments</span></span>

<span data-ttu-id="b91be-248">Alla argument till Q# anrops bara skickas som ytterligare argument när mål datorn.</span><span class="sxs-lookup"><span data-stu-id="b91be-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="b91be-249">Resultatet av `MeasureSuperpositionArray` `n=4` qubits skulle därför hämtas via</span><span class="sxs-lookup"><span data-stu-id="b91be-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="b91be-250">Ett fullständigt C#-värd program kan därför se ut så här</span><span class="sxs-lookup"><span data-stu-id="b91be-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="b91be-251">På platsen för C#-filen kan värd programmet köras från kommando raden genom att ange</span><span class="sxs-lookup"><span data-stu-id="b91be-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b91be-252">i det här fallet kommer du att se utdata som skrivits till-konsolen, ungefär som</span><span class="sxs-lookup"><span data-stu-id="b91be-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="b91be-253">På grund av kompilatorns samverkan med namn områden kan vi alternativt göra vårt Q# callables tillgängligt utan `using NamespaceName;` instruktionen och helt enkelt matcha namn områdets namn områdes rubrik.</span><span class="sxs-lookup"><span data-stu-id="b91be-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="b91be-254">Det vill säga genom att ersätta `namespace host` med `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="b91be-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="b91be-255">Inklusive resurs uppskattning</span><span class="sxs-lookup"><span data-stu-id="b91be-255">Including the resources estimator</span></span>

<span data-ttu-id="b91be-256">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Kräver en något annorlunda implementering för att hämta utdata.</span><span class="sxs-lookup"><span data-stu-id="b91be-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="b91be-257">För det första, i stället för att instansiera dem som en variabel med en `using` instruktion (som vi gör med `QuantumSimulator` ), instansierar vi omedelbart objekt av klassen via</span><span class="sxs-lookup"><span data-stu-id="b91be-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="b91be-258">Observera att i stället för en enda mål simulator som ska användas av flera Q# åtgärder har vi instansierat en för varje.</span><span class="sxs-lookup"><span data-stu-id="b91be-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="b91be-259">Detta beror på att själva objekten ändras när de används som mål datorer och resultatet kan sedan hämtas efteråt med klass metoden `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b91be-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="b91be-260">För att köra åtgärderna på resurs uppskattningarna använder vi</span><span class="sxs-lookup"><span data-stu-id="b91be-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="b91be-261">och hämtar sedan resultaten som Tabbavgränsade-värden (TSV) med `estimatorSingleQ.ToTSV()` och `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b91be-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="b91be-262">Det innebär att ett fullständigt C#-värdprogram som använder både `QuantumSimulator` och `ResourcesEstimator` kan ha formuläret:</span><span class="sxs-lookup"><span data-stu-id="b91be-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="b91be-263">vilket ger utdata som liknar</span><span class="sxs-lookup"><span data-stu-id="b91be-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="b91be-264">Q#Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="b91be-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="b91be-265">Q#Jupyter Notebooks använder i- Q# kärnan, vilket gör att du kan definiera, kompilera och köra Q# callables i en enda Notebook---alla instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="b91be-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="b91be-266">Det innebär att det är möjligt att importera och använda innehållet i filer, men det är `*.qs` Q# inte nödvändigt i körnings modellen.</span><span class="sxs-lookup"><span data-stu-id="b91be-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="b91be-267">Här kommer vi att lära dig hur du kör de Q# åtgärder som definierats ovan, men en mer bred introduktion till att använda Q# Jupyter Notebooks finns i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="b91be-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="b91be-268">Definiera åtgärder</span><span class="sxs-lookup"><span data-stu-id="b91be-268">Defining operations</span></span>

<span data-ttu-id="b91be-269">I en Q# Jupyter Notebook anger du Q# kod på samma sätt som i namn området för en Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b91be-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="b91be-270">Därför kan vi aktivera åtkomst till callables från [ Q# standard biblioteken](xref:microsoft.quantum.qsharplibintro) med `open` instruktioner för deras respektive namn rymder.</span><span class="sxs-lookup"><span data-stu-id="b91be-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="b91be-271">När du kör en cell med en sådan instruktion, är definitionerna från dessa namn områden tillgängliga i hela arbets ytan.</span><span class="sxs-lookup"><span data-stu-id="b91be-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="b91be-272">Callables från [Microsoft. Quantum. inneboende](xref:microsoft.quantum.intrinsic) och [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (t. ex. [`H`](xref:microsoft.quantum.intrinsic.h) och [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) är automatiskt tillgängliga för åtgärder som definierats i celler i Q# Jupyter notebook-datorer.</span><span class="sxs-lookup"><span data-stu-id="b91be-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="b91be-273">Detta gäller dock inte för kod som hämtas från externa Q# källfiler (en process som visas i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="b91be-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="b91be-274">På samma sätt kräver definiering av åtgärder bara att Q# koden skrivs och att cellen körs.</span><span class="sxs-lookup"><span data-stu-id="b91be-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="b91be-275">Utdata visar sedan dessa åtgärder, som sedan kan anropas från framtida celler.</span><span class="sxs-lookup"><span data-stu-id="b91be-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="b91be-276">Måldatorer</span><span class="sxs-lookup"><span data-stu-id="b91be-276">Target machines</span></span>

<span data-ttu-id="b91be-277">Funktionerna för att köra åtgärder på specifika mål datorer finns via [I Q# Magic-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="b91be-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="b91be-278">`%simulate`Använder exempelvis `QuantumSimulator` , och `%estimate` använder `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="b91be-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="b91be-279">Skicka in indata till funktioner och åtgärder</span><span class="sxs-lookup"><span data-stu-id="b91be-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="b91be-280">För närvarande kan köra Magic-kommandon endast användas med åtgärder som inte tar några argument.</span><span class="sxs-lookup"><span data-stu-id="b91be-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="b91be-281">För att kunna köra `MeasureSuperpositionArray` måste vi definiera en "wrapper"-åtgärd som sedan anropar åtgärden med argumenten:</span><span class="sxs-lookup"><span data-stu-id="b91be-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="b91be-282">Den här åtgärden kan naturligtvis användas på samma sätt som med `%estimate` och andra körnings kommandon.</span><span class="sxs-lookup"><span data-stu-id="b91be-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
