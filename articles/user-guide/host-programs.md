---
title: Sätt att köra ett Q# program
description: Översikt över olika sätt att köra Q# program. Från kommando tolken, Q# Jupyter-anteckningsböcker och klassiska värd program i python eller ett .net-språk.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231697"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="b1725-104">Sätt att köra ett Q# program</span><span class="sxs-lookup"><span data-stu-id="b1725-104">Ways to run a Q# program</span></span>

<span data-ttu-id="b1725-105">Ett av de största fördelarna med Quantum Development Kit är dess flexibilitet i plattforms-och utvecklings miljöer.</span><span class="sxs-lookup"><span data-stu-id="b1725-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="b1725-106">Det innebär dock också att nya Q# användare kan upptäcka att de många alternativen finns i [installations guiden](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b1725-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="b1725-107">På den här sidan förklarar vi vad som händer när ett Q# program körs och jämför de olika sätt som användarna kan göra.</span><span class="sxs-lookup"><span data-stu-id="b1725-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="b1725-108">En primär distinktion är att Q# du kan köra:</span><span class="sxs-lookup"><span data-stu-id="b1725-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="b1725-109">som ett fristående program, där Q# är det enda språk som ingår och programmet anropas direkt.</span><span class="sxs-lookup"><span data-stu-id="b1725-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="b1725-110">Två metoder är faktiskt i den här kategorin:</span><span class="sxs-lookup"><span data-stu-id="b1725-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="b1725-111">kommando rads gränssnittet</span><span class="sxs-lookup"><span data-stu-id="b1725-111">the command-line interface</span></span>
  - <span data-ttu-id="b1725-112">Q# Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="b1725-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="b1725-113">med ett ytterligare *värd program*, skrivet i python eller ett .net-språk (till exempel C# eller F #), som sedan anropar programmet och kan bearbeta returnerade resultat ytterligare.</span><span class="sxs-lookup"><span data-stu-id="b1725-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="b1725-114">Vi rekommenderar ett enkelt Q# program och jämför hur det kan köras för att bäst förstå de här processerna och deras skillnader.</span><span class="sxs-lookup"><span data-stu-id="b1725-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="b1725-115">Basic- Q# program</span><span class="sxs-lookup"><span data-stu-id="b1725-115">Basic Q# program</span></span>

<span data-ttu-id="b1725-116">Ett grundläggande Quantum-program kan bestå av att förbereda en qubit i en lika stor position av tillstånden $ \ket {0} $ och $ \ket {1} $, mäta den och returnera resultatet, vilket kommer att slumpmässigt vara ett av dessa två tillstånd med samma sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="b1725-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="b1725-117">Den här processen är den som är kärnan i snabb starten av [Quantum slump tals Generator](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="b1725-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="b1725-118">I Q# kan detta utföras med följande kod:</span><span class="sxs-lookup"><span data-stu-id="b1725-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="b1725-119">Den här koden kan dock endast köras av Q# .</span><span class="sxs-lookup"><span data-stu-id="b1725-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="b1725-120">För att göra det måste du skapa en [Åtgärds](xref:microsoft.quantum.qsharp.operationsandfunctions)brödtext, som sedan körs när du anropar---antingen direkt eller av en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b1725-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="b1725-121">Därför kan du skriva en åtgärd i följande format:</span><span class="sxs-lookup"><span data-stu-id="b1725-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="b1725-122">Du har definierat en åtgärd, `MeasureSuperposition` som inte tar några indata och returnerar ett värde av typen [result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span><span class="sxs-lookup"><span data-stu-id="b1725-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="b1725-123">Förutom åtgärder Q# kan även kapsla in deterministiska beräkningar i functions.</span><span class="sxs-lookup"><span data-stu-id="b1725-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="b1725-124">Förutom determinism-garantin som innebär att beräkningar som agerar på qubits måste kapslas in i åtgärder i stället för functions, är det mycket skillnad mellan åtgärder och funktion.</span><span class="sxs-lookup"><span data-stu-id="b1725-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="b1725-125">Vi refererar till dem tillsammans som *callables*.</span><span class="sxs-lookup"><span data-stu-id="b1725-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="b1725-126">Det går att anropa i en Q# fil</span><span class="sxs-lookup"><span data-stu-id="b1725-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="b1725-127">Anropet är exakt vad som anropas och körs av Q# .</span><span class="sxs-lookup"><span data-stu-id="b1725-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="b1725-128">Det krävs dock några fler tillägg för att omfatta en fullständig `*.qs` Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="b1725-129">Alla Q# typer och callables (både de som du definierar och de är inbyggda i språket) definieras i *namn områden* som ger varje fullständigt namn som sedan kan refereras.</span><span class="sxs-lookup"><span data-stu-id="b1725-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="b1725-130">Till exempel finns- [`H`](xref:Microsoft.Quantum.Intrinsic.H) och- [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) åtgärderna i [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namn områdena och (ingår i [ Q# standard biblioteken](xref:microsoft.quantum.libraries.standard.intro)).</span><span class="sxs-lookup"><span data-stu-id="b1725-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="b1725-131">Därför kan de alltid anropas via sina *fullständiga* namn `Microsoft.Quantum.Intrinsic.H(<qubit>)` och `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , men alltid göra detta skulle leda till mycket rörig kod.</span><span class="sxs-lookup"><span data-stu-id="b1725-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="b1725-132">I stället kan `open` callables refereras till med en mer koncis kort text som vi har gjort i åtgärds texten ovan.</span><span class="sxs-lookup"><span data-stu-id="b1725-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="b1725-133">Den fullständiga Q# filen som innehåller vår åtgärd skulle därför bestå av att definiera vår egen namnrymd, öppna namn områdena för de callables som vår åtgärd använder och sedan vår åtgärd:</span><span class="sxs-lookup"><span data-stu-id="b1725-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="b1725-134">Namn områden kan också vara *aliasade* när de öppnas, vilket kan vara användbart om anrops bara/typnamn i två namn områden står i konflikt.</span><span class="sxs-lookup"><span data-stu-id="b1725-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="b1725-135">Vi kan till exempel använda `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ovanstående, och sedan anropa `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="b1725-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-136">Ett undantag till allt detta är [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namn området, som alltid öppnas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b1725-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="b1725-137">Därför kan callables som [`Length`](xref:Microsoft.Quantum.Core.Length) alltid användas direkt.</span><span class="sxs-lookup"><span data-stu-id="b1725-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="b1725-138">Körs på mål datorer</span><span class="sxs-lookup"><span data-stu-id="b1725-138">Running on target machines</span></span>

<span data-ttu-id="b1725-139">Nu är den allmänna körnings modellen för ett Q# program avmarkerad.</span><span class="sxs-lookup"><span data-stu-id="b1725-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="b1725-140">För det första har det speciella anropet att köras åtkomst till alla andra callables och typer som definierats i samma namnrymd.</span><span class="sxs-lookup"><span data-stu-id="b1725-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="b1725-141">De kommer även åt dem från alla [ Q# bibliotek](xref:microsoft.quantum.libraries), men de måste refereras antingen via deras fullständiga namn eller genom användning av `open` instruktioner som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="b1725-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="b1725-142">Själva anropet körs sedan på en *[måldator](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="b1725-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="b1725-143">Sådana mål datorer kan vara faktiska Quantum-maskinvara eller flera simulatorer som är tillgängliga som en del av QDK.</span><span class="sxs-lookup"><span data-stu-id="b1725-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="b1725-144">För våra behov är den mest användbara mål datorn en instans av [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` som beräknar programmets beteende som om det kördes på en dator som är en brus fri.</span><span class="sxs-lookup"><span data-stu-id="b1725-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="b1725-145">Hittills har vi beskrivit vad som händer när en speciell Q# anrop körs.</span><span class="sxs-lookup"><span data-stu-id="b1725-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="b1725-146">Oavsett om används Q# i ett fristående program eller med ett värd program, är den här generella processen mer eller mindre---, och därför är QDK flexibiliteten.</span><span class="sxs-lookup"><span data-stu-id="b1725-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="b1725-147">Skillnaderna mellan olika sätt att anropa i Quantum Development Kit visas därför i *hur* det kan anropas Q# för att köras, och i vilket sätt resultat returneras.</span><span class="sxs-lookup"><span data-stu-id="b1725-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="b1725-148">Mer specifikt kretsar skiljer sig runt:</span><span class="sxs-lookup"><span data-stu-id="b1725-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="b1725-149">Indikerar vilket anrop som ska Q# köras</span><span class="sxs-lookup"><span data-stu-id="b1725-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="b1725-150">Hur potentiella anrops bara argument anges</span><span class="sxs-lookup"><span data-stu-id="b1725-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="b1725-151">Ange mål datorn som den ska köras på</span><span class="sxs-lookup"><span data-stu-id="b1725-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="b1725-152">Hur resultat returneras</span><span class="sxs-lookup"><span data-stu-id="b1725-152">How any results are returned</span></span>

<span data-ttu-id="b1725-153">Först diskuterar vi hur detta görs med det Q# fristående programmet från kommando tolken och fortsätter sedan att använda python-och C#-värd program.</span><span class="sxs-lookup"><span data-stu-id="b1725-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="b1725-154">Vi reserverar det fristående programmet för Q# Jupyter Notebooks för sista, eftersom till skillnad från de tre första, är den primära funktionen inte en lokal Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-155">Även om vi inte illustrerar det i de här exemplen, är en gemensam lösning mellan körnings metoderna att alla meddelanden som skrivs ut inifrån Q# programmet (av [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) eller [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) till exempel) alltid skrivs ut till respektive konsol.</span><span class="sxs-lookup"><span data-stu-id="b1725-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="b1725-156">Q# från kommando tolken</span><span class="sxs-lookup"><span data-stu-id="b1725-156">Q# from the command prompt</span></span>
<span data-ttu-id="b1725-157">Ett av de enklaste sätten att komma igång med att skriva Q# program är att undvika att behöva oroa dig för separata filer och ett andra språk helt och hållet.</span><span class="sxs-lookup"><span data-stu-id="b1725-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="b1725-158">Med hjälp av Visual Studio Code eller Visual Studio med QDK-tillägget kan du använda ett sömlöst arbets flöde där vi kör Q# callables från endast en enda Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="b1725-159">För detta kommer vi att köra programmet genom att ange</span><span class="sxs-lookup"><span data-stu-id="b1725-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="b1725-160">i kommando tolken.</span><span class="sxs-lookup"><span data-stu-id="b1725-160">at the command prompt.</span></span>
<span data-ttu-id="b1725-161">Det enklaste arbets flödet är när terminalens katalog plats är samma som Q# filen, som enkelt kan hanteras tillsammans Q# med fil redigering genom att använda den integrerade terminalen i vs Code, till exempel.</span><span class="sxs-lookup"><span data-stu-id="b1725-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="b1725-162">[ `dotnet run` Kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) godkänner dock flera alternativ, och programmet kan också köras från en annan plats genom att bara ange `--project <PATH>` platsen för Q# filen.</span><span class="sxs-lookup"><span data-stu-id="b1725-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="b1725-163">Lägg till Start punkt till Q# fil</span><span class="sxs-lookup"><span data-stu-id="b1725-163">Add entry point to Q# file</span></span>

<span data-ttu-id="b1725-164">De flesta Q# filer kommer att innehålla mer än ett anrops bara, så det är naturligt att låta kompileraren ta reda på *vilket* anrop som kan köras när vi tillhandahåller `dotnet run` kommandot.</span><span class="sxs-lookup"><span data-stu-id="b1725-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="b1725-165">Detta görs med en enkel ändring i Q# själva filen:</span><span class="sxs-lookup"><span data-stu-id="b1725-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="b1725-166">Lägg till en rad med `@EntryPoint()` direkt föregående anrop.</span><span class="sxs-lookup"><span data-stu-id="b1725-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="b1725-167">Vår fil ovan skulle därför bli</span><span class="sxs-lookup"><span data-stu-id="b1725-167">Our file from above would therefore become</span></span>
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

<span data-ttu-id="b1725-168">Nu kommer ett anrop `dotnet run` från kommando tolken att `MeasureSuperposition` köras, och det returnerade värdet skrivs sedan direkt till terminalen.</span><span class="sxs-lookup"><span data-stu-id="b1725-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="b1725-169">Så visas antingen `One` eller `Zero` skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="b1725-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="b1725-170">Observera att det inte spelar någon roll om du har angett fler callables under den, så `MeasureSuperposition` körs endast.</span><span class="sxs-lookup"><span data-stu-id="b1725-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="b1725-171">Dessutom är det inget problem om ditt anrop bara innehåller [dokumentations kommentarer](xref:microsoft.quantum.qsharp.comments#documentation-comments) före dess deklaration, så `@EntryPoint()` kan attributet placeras ovanför dem.</span><span class="sxs-lookup"><span data-stu-id="b1725-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="b1725-172">Anrops bara argument</span><span class="sxs-lookup"><span data-stu-id="b1725-172">Callable arguments</span></span>

<span data-ttu-id="b1725-173">Hittills har vi bara sett en åtgärd som inte kräver några indata.</span><span class="sxs-lookup"><span data-stu-id="b1725-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="b1725-174">Anta att vi ville utföra en liknande åtgärd, men på flera qubits---det antal som tillhandahålls som ett argument.</span><span class="sxs-lookup"><span data-stu-id="b1725-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="b1725-175">Sådan åtgärd kan skrivas som</span><span class="sxs-lookup"><span data-stu-id="b1725-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="b1725-176">där det returnerade värdet är en matris av mått resultatet.</span><span class="sxs-lookup"><span data-stu-id="b1725-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="b1725-177">Observera att [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) och [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) är i [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namn områdena och som kräver ytterligare `open` instruktioner för varje.</span><span class="sxs-lookup"><span data-stu-id="b1725-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="b1725-178">Om vi flyttar `@EntryPoint()` attributet till före den här nya åtgärden (Observera att det bara kan finnas en sådan rad i en fil), försöker köra det med bara `dotnet run` resulterar i ett fel meddelande som anger vilka ytterligare kommando rads alternativ som krävs och hur du uttrycker dem.</span><span class="sxs-lookup"><span data-stu-id="b1725-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="b1725-179">Det allmänna formatet för kommando raden är faktiskt `dotnet run [options]` och det finns argument som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="b1725-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="b1725-180">I det här fallet saknas argumentet `n` , och det visar att vi behöver tillhandahålla alternativet `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b1725-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="b1725-181">För att köra `MeasureSuperpositionArray` för `n=4` qubits använder vi därför</span><span class="sxs-lookup"><span data-stu-id="b1725-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="b1725-182">ge utdata som liknar</span><span class="sxs-lookup"><span data-stu-id="b1725-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="b1725-183">Den här kursen utökar till flera argument.</span><span class="sxs-lookup"><span data-stu-id="b1725-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-184">Argument namn som definieras i `camelCase` har ändrats något av kompilatorn som ska godkännas som Q# indata.</span><span class="sxs-lookup"><span data-stu-id="b1725-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="b1725-185">Om till exempel i stället för `n` , vi använde namnet `numQubits` ovan, skulle den här indatan tillhandahållas på kommando raden via `--num-qubits 4` i stället för `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="b1725-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="b1725-186">Fel meddelandet innehåller också andra alternativ som kan användas, inklusive hur du ändrar mål datorn.</span><span class="sxs-lookup"><span data-stu-id="b1725-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="b1725-187">Olika mål datorer</span><span class="sxs-lookup"><span data-stu-id="b1725-187">Different target machines</span></span>

<span data-ttu-id="b1725-188">Eftersom resultatet från våra åtgärder hittills har varit det förväntade resultatet av sin åtgärd på verkliga qubits, är det uppenbart att standard mål datorn från kommando raden är en Quantum-simulator med full status `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="b1725-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="b1725-189">Vi kan dock instruera callables att köras på en speciell måldator med alternativet `--simulator` (eller kort `-s` ).</span><span class="sxs-lookup"><span data-stu-id="b1725-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="b1725-190">Vi kan till exempel köra den på [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="b1725-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="b1725-191">De utskrivna utdata är sedan</span><span class="sxs-lookup"><span data-stu-id="b1725-191">The printed output is then</span></span>

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

<span data-ttu-id="b1725-192">Mer information om vad dessa mått anger finns i [resurs uppskattningen: statistik rapporteras](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="b1725-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="b1725-193">Sammanfattning av kommando rads körning</span><span class="sxs-lookup"><span data-stu-id="b1725-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="b1725-194">Icke- Q# `dotnet run` alternativ</span><span class="sxs-lookup"><span data-stu-id="b1725-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="b1725-195">Som vi nämnde ovan med `--project` alternativet godkänner [ `dotnet run` kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) också alternativ som inte är relaterade till de Q# anrops bara argumenten.</span><span class="sxs-lookup"><span data-stu-id="b1725-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="b1725-196">Om du tillhandahåller båda typerna av alternativ `dotnet` måste de-/regionsspecifika alternativen anges först, följt av en avgränsare `--` och sedan de Q# -/regionsspecifika alternativen.</span><span class="sxs-lookup"><span data-stu-id="b1725-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="b1725-197">Om du till exempel anger en sökväg tillsammans med en nummer qubits för åtgärden ovan, skulle det köras via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b1725-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="b1725-198">Q# med värd program</span><span class="sxs-lookup"><span data-stu-id="b1725-198">Q# with host programs</span></span>

<span data-ttu-id="b1725-199">Med vår Q# fil i handen är ett alternativ för att anropa en åtgärd eller funktion direkt från kommando tolken att använda ett *värd program* i ett annat klassiskt språk.</span><span class="sxs-lookup"><span data-stu-id="b1725-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="b1725-200">Mer specifikt kan detta göras med antingen python eller ett .NET-språk, till exempel C# eller F # (för det kortfattat vi bara detaljerat C# här).</span><span class="sxs-lookup"><span data-stu-id="b1725-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="b1725-201">Lite mer konfiguration krävs för att aktivera samverkan, men informationen finns i [installations guiderna](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b1725-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b1725-202">I en kortfattat så Jenkins innehåller situationen nu en värd program fil (till exempel `*.py` eller `*.cs` ) på samma plats som vår Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="b1725-203">Det är nu *värd* programmet som körs och när det körs kan den anropa vissa Q# åtgärder och funktioner från Q# filen.</span><span class="sxs-lookup"><span data-stu-id="b1725-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="b1725-204">Kärnornas kärna baseras på Q# kompilatorn som gör innehållet i Q# filen tillgängligt för värd programmet så att de kan anropas.</span><span class="sxs-lookup"><span data-stu-id="b1725-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="b1725-205">En av de främsta fördelarna med att använda ett värd program är att de klassiska data som returneras av Q# programmet kan bearbetas ytterligare på värd språket.</span><span class="sxs-lookup"><span data-stu-id="b1725-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="b1725-206">Detta kan bestå av en avancerad data bearbetning (till exempel något som inte kan utföras internt i Q# ) och sedan anropa ytterligare Q# åtgärder baserat på dessa resultat eller något som är enkelt som att rita Q# resultaten.</span><span class="sxs-lookup"><span data-stu-id="b1725-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="b1725-207">Det allmänna schemat visas här och vi diskuterar de olika implementeringarna för python och C# nedan.</span><span class="sxs-lookup"><span data-stu-id="b1725-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="b1725-208">Ett exempel som använder ett F # Host-program finns i [.net-samverkan exempel](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b1725-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="b1725-209">`@EntryPoint()`Attributet som används för Q# program kan inte användas med värd program.</span><span class="sxs-lookup"><span data-stu-id="b1725-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="b1725-210">Ett fel genereras om det finns i den Q# fil som anropas av en värd.</span><span class="sxs-lookup"><span data-stu-id="b1725-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="b1725-211">Om du vill arbeta med olika värd program krävs inga ändringar i en `*.qs` Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="b1725-212">Följande värd program implementerar allt arbete med samma Q# fil:</span><span class="sxs-lookup"><span data-stu-id="b1725-212">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="b1725-213">Välj den flik som motsvarar värd språket i intresse.</span><span class="sxs-lookup"><span data-stu-id="b1725-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="b1725-214">Python</span><span class="sxs-lookup"><span data-stu-id="b1725-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="b1725-215">Ett python-värdprogram skapas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b1725-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="b1725-216">Importera `qsharp` modulen som registrerar modulens inläsare för Q# interoperabilitet.</span><span class="sxs-lookup"><span data-stu-id="b1725-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b1725-217">Detta gör Q# att namn områden kan visas som python-moduler, från vilka vi kan importera Q# callables.</span><span class="sxs-lookup"><span data-stu-id="b1725-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="b1725-218">Observera att det tekniskt sett inte är Q# callablest som importeras, men hellre python-stub-stub som tillåter att de anropar dem.</span><span class="sxs-lookup"><span data-stu-id="b1725-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="b1725-219">De fungerar som objekt av python-klasser.</span><span class="sxs-lookup"><span data-stu-id="b1725-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="b1725-220">Vi använder metoder för dessa objekt för att ange de mål datorer som vi skickar åtgärden till när programmet körs.</span><span class="sxs-lookup"><span data-stu-id="b1725-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="b1725-221">Importera de Q# callables som vi kommer att anropa direkt---i det här fallet `MeasureSuperposition` och `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="b1725-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="b1725-222">När `qsharp` modulen har importer ATS kan du också importera callables direkt från Q# biblioteks namn områdena.</span><span class="sxs-lookup"><span data-stu-id="b1725-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="b1725-223">Bland alla andra python-koder kan du nu anropa dessa callables på specifika mål datorer och tilldela deras returer till variabler (om de returnerar ett värde) för att användas.</span><span class="sxs-lookup"><span data-stu-id="b1725-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="b1725-224">Ange mål datorer</span><span class="sxs-lookup"><span data-stu-id="b1725-224">Specifying target machines</span></span>
<span data-ttu-id="b1725-225">Att anropa en åtgärd som ska köras på en särskild måldator görs via olika python-metoder för det importerade objektet.</span><span class="sxs-lookup"><span data-stu-id="b1725-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="b1725-226">Till exempel `.simulate(<args>)` använder, för `QuantumSimulator` att köra åtgärden, men gör det `.estimate_resources(<args>)` på `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="b1725-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="b1725-227">Skicka indata till Q\#</span><span class="sxs-lookup"><span data-stu-id="b1725-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="b1725-228">Argument för anrop kan anges Q# i form av ett nyckelord, där nyckelordet är argument namnet i den Q# anropade definitionen.</span><span class="sxs-lookup"><span data-stu-id="b1725-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="b1725-229">Det vill säga är `MeasureSuperpositionArray.simulate(n=4)` giltigt, vilket `MeasureSuperpositionArray.simulate(4)` skulle resultera i ett fel.</span><span class="sxs-lookup"><span data-stu-id="b1725-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="b1725-230">Det innebär att python-värd programmet</span><span class="sxs-lookup"><span data-stu-id="b1725-230">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="b1725-231">resulterar i utdata som följande:</span><span class="sxs-lookup"><span data-stu-id="b1725-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b1725-232">Använda Q# kod från andra projekt eller paket</span><span class="sxs-lookup"><span data-stu-id="b1725-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b1725-233">Som standard `import qsharp` läser kommandot in alla `.qs` filer i den aktuella mappen och gör att deras Q# åtgärder och funktioner kan användas i python-skriptet.</span><span class="sxs-lookup"><span data-stu-id="b1725-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="b1725-234">Om du vill läsa in Q# kod från en annan mapp kan du använda [ `qsharp.projects` API: et](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) för att lägga till en referens till en `.csproj` fil för ett Q# projekt (det vill säga ett projekt som refererar `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="b1725-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="b1725-235">Det här kommandot kommer att kompilera alla `.qs` filer i mappen som innehåller `.csproj` undermapparna och.</span><span class="sxs-lookup"><span data-stu-id="b1725-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="b1725-236">Det kommer också att läsa in alla paket som refereras via `PackageReference` eller Q# projekt som refereras till via `ProjectReference` i `.csproj` filen.</span><span class="sxs-lookup"><span data-stu-id="b1725-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="b1725-237">Följande python-kod importerar till exempel ett externt projekt, refererar till dess sökväg i förhållande till den aktuella mappen och anropar en av dess Q# åtgärder:</span><span class="sxs-lookup"><span data-stu-id="b1725-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="b1725-238">Detta resulterar i utdata som följande:</span><span class="sxs-lookup"><span data-stu-id="b1725-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="b1725-239">Q#Använd [ `qsharp.packages` API: et](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)för att läsa in externa paket som innehåller kod.</span><span class="sxs-lookup"><span data-stu-id="b1725-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="b1725-240">Om Q# koden i den aktuella mappen är beroende av externa projekt eller paket kan du se fel när du kör `import qsharp` , eftersom beroendena ännu inte har lästs in.</span><span class="sxs-lookup"><span data-stu-id="b1725-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="b1725-241">Om du vill läsa in nödvändiga externa paket eller Q# projekt under `import qsharp` kommandot kontrollerar du att mappen med python-skriptet innehåller en `.csproj` fil som refererar till den `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b1725-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b1725-242">I `.csproj` lägger du till egenskapen `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` i `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="b1725-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b1725-243">Detta instruerar mig Q# att rekursivt läsa in alla `ProjectReference` eller `PackageReference` objekt som finns i det `.csproj` under `import qsharp` kommandot.</span><span class="sxs-lookup"><span data-stu-id="b1725-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="b1725-244">Här är till exempel en enkel `.csproj` fil som gör att jag Q# kan läsa in `Microsoft.Quantum.Chemistry` paketet automatiskt:</span><span class="sxs-lookup"><span data-stu-id="b1725-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="b1725-245">För närvarande krävs den här anpassade `<IQSharpLoadAutomatically>` egenskapen av python-värdar, men i framtiden kan detta bli standard beteendet för en `.csproj` fil som finns i samma mapp som python-skriptet.</span><span class="sxs-lookup"><span data-stu-id="b1725-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-246">För närvarande `<QsharpCompile>` ignoreras inställningen i av `.csproj` python-värdar, och alla `.qs` filer i mappen i `.csproj` (inklusive undermappar) läses in och kompileras.</span><span class="sxs-lookup"><span data-stu-id="b1725-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b1725-247">Stöd för `.csproj` inställningar kommer att förbättras i framtiden (se [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) för mer information).</span><span class="sxs-lookup"><span data-stu-id="b1725-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="b1725-248">C#</span><span class="sxs-lookup"><span data-stu-id="b1725-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b1725-249">Ett C#-värdprogram har flera komponenter och fungerar mycket nära vissa komponenter i QDK, till exempel simulatorer, som är inbyggda i C#.</span><span class="sxs-lookup"><span data-stu-id="b1725-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="b1725-250">Q#Kompilatorn fungerar här genom att generera ett likvärdigt namngivet C#-namnområde från Q# namn området i vår Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="b1725-251">Den genererar ytterligare en motsvarande namngiven C#-klass för var och en av de Q# callables eller typer som definieras däri.</span><span class="sxs-lookup"><span data-stu-id="b1725-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="b1725-252">Först gör vi några klasser som används i vårt värd program `using` som är tillgängliga med instruktioner, som är ungefär analagousa till `open` uttrycken i vår Q# fil:</span><span class="sxs-lookup"><span data-stu-id="b1725-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="b1725-253">Härnäst deklarerar vi vårt C#-namnrum, några andra bitar och delar (se hela kod blocket nedan) och sedan en klassisk programmering som vi vill ha (till exempel att beräkna argument för Q# callables).</span><span class="sxs-lookup"><span data-stu-id="b1725-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="b1725-254">Den senare är inte nödvändig i vårt fall, men ett exempel på en sådan användning finns i  [exempel på .net-interoperabilitet](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b1725-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="b1725-255">Måldatorer</span><span class="sxs-lookup"><span data-stu-id="b1725-255">Target machines</span></span>

<span data-ttu-id="b1725-256">Kom tillbaka till Q# , vi måste skapa en instans av den mål dator vi kommer att köra våra åtgärder på.</span><span class="sxs-lookup"><span data-stu-id="b1725-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="b1725-257">Att använda andra mål datorer är lika enkelt som att instansiera en annan, även om sättet att göra så och bearbetning av returerna kan vara något annorlunda.</span><span class="sxs-lookup"><span data-stu-id="b1725-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="b1725-258">För det kortfattat går vi till [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) för tillfället och inkluderar [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [nedan](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="b1725-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="b1725-259">Varje C#-klass som genereras från Q# åtgärder har en `Run` metod, vars första argument måste vara mål datorns instans.</span><span class="sxs-lookup"><span data-stu-id="b1725-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="b1725-260">Så att du kan köra `MeasureSuperposition` på `QuantumSimulator` , vi använder `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="b1725-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="b1725-261">De returnerade resultaten kan sedan tilldelas variabler i C#:</span><span class="sxs-lookup"><span data-stu-id="b1725-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="b1725-262">`Run`Metoden körs asynkront eftersom detta är fallet för verkligt Quantum-maskinvara, och därför `await` blockerar nyckelordet ytterligare bearbetning tills aktiviteten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="b1725-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="b1725-263">Om det Q# inte finns några returnerade returer (till exempel om den har retur typen `Unit` ) kan körningen fortfarande göras på samma sätt utan att tilldela den till en variabel.</span><span class="sxs-lookup"><span data-stu-id="b1725-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="b1725-264">I så fall skulle hela raden helt enkelt bestå av</span><span class="sxs-lookup"><span data-stu-id="b1725-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="b1725-265">Argument</span><span class="sxs-lookup"><span data-stu-id="b1725-265">Arguments</span></span>

<span data-ttu-id="b1725-266">Alla argument till Q# anrops bara skickas som ytterligare argument efter mål datorn.</span><span class="sxs-lookup"><span data-stu-id="b1725-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="b1725-267">Resultatet av `MeasureSuperpositionArray` `n=4` qubits skulle därför hämtas via</span><span class="sxs-lookup"><span data-stu-id="b1725-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="b1725-268">Ett fullständigt C#-värd program kan därför se ut så här</span><span class="sxs-lookup"><span data-stu-id="b1725-268">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="b1725-269">På C#-filens plats kan värd programmet köras från kommando tolken genom att ange</span><span class="sxs-lookup"><span data-stu-id="b1725-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b1725-270">i det här fallet kommer du att se utdata som skrivits till-konsolen, ungefär som</span><span class="sxs-lookup"><span data-stu-id="b1725-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="b1725-271">På grund av kompilatorns samverkan med namn områden kan vi alternativt göra vårt Q# callables tillgängligt utan `using NamespaceName;` instruktionen och helt enkelt matcha namn områdets namn områdes rubrik.</span><span class="sxs-lookup"><span data-stu-id="b1725-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="b1725-272">Det vill säga genom att ersätta `namespace host` med `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="b1725-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="b1725-273">Inklusive resurs uppskattning</span><span class="sxs-lookup"><span data-stu-id="b1725-273">Including the resources estimator</span></span>

<span data-ttu-id="b1725-274">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Kräver en något annorlunda implementering för att hämta utdata.</span><span class="sxs-lookup"><span data-stu-id="b1725-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="b1725-275">För det första, i stället för att instansiera dem som en variabel med en `using` instruktion (som vi gör med `QuantumSimulator` ), instansierar vi omedelbart objekt av klassen via</span><span class="sxs-lookup"><span data-stu-id="b1725-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="b1725-276">Observera att i stället för en enda mål simulator som ska användas av flera Q# åtgärder har vi instansierat en för varje.</span><span class="sxs-lookup"><span data-stu-id="b1725-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="b1725-277">Detta beror på att själva objekten ändras när de används som mål datorer och resultatet kan sedan hämtas efteråt med klass metoden `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b1725-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="b1725-278">För att köra åtgärderna på resurs uppskattningarna använder vi</span><span class="sxs-lookup"><span data-stu-id="b1725-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="b1725-279">och hämtar sedan resultaten som Tabbavgränsade-värden (TSV) med `estimatorSingleQ.ToTSV()` och `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b1725-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="b1725-280">Det innebär att ett fullständigt C#-värdprogram som använder både `QuantumSimulator` och `ResourcesEstimator` kan ha formuläret:</span><span class="sxs-lookup"><span data-stu-id="b1725-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="b1725-281">vilket ger utdata som liknar</span><span class="sxs-lookup"><span data-stu-id="b1725-281">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="b1725-282">Q# Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="b1725-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="b1725-283">Q# Jupyter Notebooks använder i- Q# kärnan, vilket gör att du kan definiera, kompilera och köra Q# callables i en enda Notebook---alla instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="b1725-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="b1725-284">Det innebär att det är möjligt att importera och använda innehållet i `*.qs` Q# filer, men det är inte nödvändigt i körnings modellen.</span><span class="sxs-lookup"><span data-stu-id="b1725-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="b1725-285">Här kommer vi att lära dig hur du kör de Q# åtgärder som definierats ovan, men en mer bred introduktion till att använda Q# Jupyter Notebooks finns i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="b1725-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="b1725-286">Definiera åtgärder</span><span class="sxs-lookup"><span data-stu-id="b1725-286">Defining operations</span></span>

<span data-ttu-id="b1725-287">I en Q# Jupyter Notebook anger du Q# kod på samma sätt som i namn området för en Q# fil.</span><span class="sxs-lookup"><span data-stu-id="b1725-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="b1725-288">Därför kan vi aktivera åtkomst till callables från [ Q# standard biblioteken](xref:microsoft.quantum.libraries.standard.intro) med `open` instruktioner för deras respektive namn rymder.</span><span class="sxs-lookup"><span data-stu-id="b1725-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="b1725-289">När du kör en cell med en sådan instruktion, är definitionerna från dessa namn områden tillgängliga i hela arbets ytan.</span><span class="sxs-lookup"><span data-stu-id="b1725-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-290">Callables från [Microsoft. Quantum. inneboende](xref:Microsoft.Quantum.Intrinsic) och [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (till exempel [`H`](xref:Microsoft.Quantum.Intrinsic.H) och [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) är automatiskt tillgängliga för åtgärder som definierats i celler i Q# Jupyter-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="b1725-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="b1725-291">Detta gäller dock inte för kod som hämtas från externa Q# källfiler (en process som visas i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="b1725-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="b1725-292">På samma sätt kräver definiering av åtgärder bara att Q# koden skrivs och att cellen körs.</span><span class="sxs-lookup"><span data-stu-id="b1725-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="b1725-293">Utdata visar sedan dessa åtgärder, som sedan kan anropas från framtida celler.</span><span class="sxs-lookup"><span data-stu-id="b1725-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="b1725-294">Måldatorer</span><span class="sxs-lookup"><span data-stu-id="b1725-294">Target machines</span></span>

<span data-ttu-id="b1725-295">Funktionerna för att köra åtgärder på specifika mål datorer finns via [I Q# Magic-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="b1725-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="b1725-296">`%simulate`Använder exempelvis `QuantumSimulator` , och `%estimate` använder `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="b1725-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="b1725-297">Skicka in indata till funktioner och åtgärder</span><span class="sxs-lookup"><span data-stu-id="b1725-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="b1725-298">Om du vill skicka indata till Q# åtgärder kan argumenten skickas som `key=value` par till kommandot Run Magic.</span><span class="sxs-lookup"><span data-stu-id="b1725-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="b1725-299">För att kunna köra `MeasureSuperpositionArray` med fyra qubits kan vi köra `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="b1725-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="b1725-300">Det här mönstret kan användas på samma sätt med `%estimate` och andra körnings kommandon.</span><span class="sxs-lookup"><span data-stu-id="b1725-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b1725-301">Använda Q# kod från andra projekt eller paket</span><span class="sxs-lookup"><span data-stu-id="b1725-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b1725-302">Som standard läser ett Q# Jupyter Notebook alla `.qs` filer i den aktuella mappen och gör att de kan Q# användas i den bärbara datorn.</span><span class="sxs-lookup"><span data-stu-id="b1725-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="b1725-303">[ `%who` Kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) visar alla åtgärder och funktioner som är tillgängliga för närvarande Q# .</span><span class="sxs-lookup"><span data-stu-id="b1725-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="b1725-304">Om du vill läsa in Q# kod från en annan mapp kan du använda [ `%project` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) för att lägga till en referens till en `.csproj` fil för ett Q# projekt (det vill säga ett projekt som refererar till `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="b1725-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="b1725-305">Med det här kommandot kompileras `.qs` filer i mappen som innehåller `.csproj` (och undermapparna).</span><span class="sxs-lookup"><span data-stu-id="b1725-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="b1725-306">Det kommer också att läsa in alla paket som refereras via `PackageReference` eller Q# projekt som refereras till via `ProjectReference` i `.csproj` filen.</span><span class="sxs-lookup"><span data-stu-id="b1725-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="b1725-307">Som exempel simulerar följande celler en Q# åtgärd från ett externt projekt, där projekt Sök vägen refereras till i förhållande till den aktuella mappen:</span><span class="sxs-lookup"><span data-stu-id="b1725-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="b1725-308">Om du vill läsa in externa paket som innehåller Q# kod använder du [ `%package` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="b1725-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="b1725-309">När du läser in ett paket blir det också tillgängligt eventuella anpassade Magic-kommandon eller Visa kodare som finns i alla sammansättningar som ingår i paketet.</span><span class="sxs-lookup"><span data-stu-id="b1725-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="b1725-310">Om du vill läsa in externa paket eller Q# projekt på Notebook intialization-tid, se till att mappen Notebook innehåller en `.csproj` fil som refererar till `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b1725-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b1725-311">I `.csproj` lägger du till egenskapen `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` i `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="b1725-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b1725-312">Detta instruerar mig Q# att rekursivt läsa in alla `ProjectReference` eller `PackageReference` objekt som finns i den `.csproj` bärbara datorns inläsnings tid.</span><span class="sxs-lookup"><span data-stu-id="b1725-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="b1725-313">Här är till exempel en enkel `.csproj` fil som gör att jag Q# kan läsa in `Microsoft.Quantum.Chemistry` paketet automatiskt:</span><span class="sxs-lookup"><span data-stu-id="b1725-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="b1725-314">För närvarande krävs den här anpassade `<IQSharpLoadAutomatically>` egenskapen av Q# Jupyter Notebook värdar, men i framtiden kan detta bli standard beteendet för en `.csproj` fil som finns i samma mapp som Notebook-filen.</span><span class="sxs-lookup"><span data-stu-id="b1725-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="b1725-315">För närvarande `<QsharpCompile>` ignoreras inställningen i av `.csproj` Q# Jupyter Notebook värdar, och alla `.qs` filer i mappen i `.csproj` (inklusive undermappar) läses in och kompileras.</span><span class="sxs-lookup"><span data-stu-id="b1725-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b1725-316">Stöd för `.csproj` inställningar kommer att förbättras i framtiden (se [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) för mer information).</span><span class="sxs-lookup"><span data-stu-id="b1725-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
