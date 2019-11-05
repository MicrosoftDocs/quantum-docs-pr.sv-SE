---
title: Kör Grovers sökalgoritm i Q# – Quantum Development Kit
description: Skapa ett Q#-projekt som visar Grovers algoritm, en av de legendariska kvantalgoritmerna.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443944"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="33e64-103">Snabbstart: Implementera Grovers sökalgoritm i Q#</span><span class="sxs-lookup"><span data-stu-id="33e64-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="33e64-104">I den här snabbstarten får du lära dig att skapa och köra Grover-sökning som påskyndar sökningen i ostrukturerade data.</span><span class="sxs-lookup"><span data-stu-id="33e64-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="33e64-105">Grovers sökning är en av de mest populära kvantberäkningsalgoritmerna. Den här relativt lilla Q#-implementeringen ger dig en uppfattning om några av fördelarna med programmering av kvantlösningar med kvantprogrammeringsspråket Q# som på hög nivå uttrycker kvantalgoritmer.</span><span class="sxs-lookup"><span data-stu-id="33e64-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="33e64-106">I slutet av guiden kommer du att se att simuleringen hittar en specifik sträng i listan med osorterade poster på en bråkdel av den tid det skulle ta att söka igenom hela listan på en klassisk dator.</span><span class="sxs-lookup"><span data-stu-id="33e64-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="33e64-107">Grovers algoritm söker i en lista med ostrukturerade data efter vissa objekt.</span><span class="sxs-lookup"><span data-stu-id="33e64-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="33e64-108">Den kan till exempel svara på frågan: Är det här kortet som drogs ur en kortlek hjärter ess?</span><span class="sxs-lookup"><span data-stu-id="33e64-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="33e64-109">Märkningen av det speciella objektet kallas för _markerad indata_.</span><span class="sxs-lookup"><span data-stu-id="33e64-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="33e64-110">Med hjälp av Grovers sökalgoritm kommer kvantdatorn garanterat att utföra sökningen i färre steg än antalet objekt i listan som du söker i, något som inte kan göras av en klassisk algoritm.</span><span class="sxs-lookup"><span data-stu-id="33e64-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="33e64-111">Den ökade hastigheten när en kortlek ska genomsökas är försumbar, men i listor som innehåller miljontals eller miljardtals objekt blir det mer viktigt.</span><span class="sxs-lookup"><span data-stu-id="33e64-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="33e64-112">Du kan bygga Grovers sökalgoritm med bara några rader kod.</span><span class="sxs-lookup"><span data-stu-id="33e64-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33e64-113">Nödvändiga komponenter</span><span class="sxs-lookup"><span data-stu-id="33e64-113">Prerequisites</span></span>

- <span data-ttu-id="33e64-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="33e64-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="33e64-115">Vad gör Grovers sökalgoritm?</span><span class="sxs-lookup"><span data-stu-id="33e64-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="33e64-116">Grovers algoritm frågar om ett objekt i en lista är det som vi söker efter.</span><span class="sxs-lookup"><span data-stu-id="33e64-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="33e64-117">Detta görs genom att en kvantsuperposition skapas av indexen i listan med respektive koefficient, eller sannolikhetsamplitud, vilket utgör sannolikheten för att det aktuella indexet är det som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="33e64-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="33e64-118">Algoritmen består av två steg som ökar indexkoefficienten som vi söker efter inkrementellt, fram till att sannolikhetsamplituden för den aktuella koefficienten blir ett.</span><span class="sxs-lookup"><span data-stu-id="33e64-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="33e64-119">Antalet stegvisa ökningar är färre än antalet objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="33e64-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="33e64-120">Det här är anledningen till att Grovers sökalgoritm utför sökningen i färre steg än en klassisk algoritm.</span><span class="sxs-lookup"><span data-stu-id="33e64-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Funktionsdiagram över Grovers sökalgoritm](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="33e64-122">Skriva koden</span><span class="sxs-lookup"><span data-stu-id="33e64-122">Write the code</span></span>

1. <span data-ttu-id="33e64-123">Med hjälp av Quantum Development Kit [skapas ett nytt Q#-projekt](xref:microsoft.quantum.howto.createproject) som kallas `Grover` i valfri utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="33e64-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="33e64-124">I projektfilen `Operations.qs` lägger du till följande kod:</span><span class="sxs-lookup"><span data-stu-id="33e64-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="33e64-125">Definiera listan som vi söker i genom att skapa den nya filen `Reflections.qs` där du klistrar in följande kod:</span><span class="sxs-lookup"><span data-stu-id="33e64-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="33e64-126">Åtgärden `ReflectAboutMarked` definierar den markerade indata som du söker efter: Strängen med alternerande nollor och ettor.</span><span class="sxs-lookup"><span data-stu-id="33e64-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="33e64-127">I det här exemplet hårdkodas markerad indata, vilket kan utökas till att söka efter olika indata eller generaliseras för alla indata.</span><span class="sxs-lookup"><span data-stu-id="33e64-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="33e64-128">Kör sedan ditt nya Q#-program för att hitta objektet som markerats med `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="33e64-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="33e64-129">Python med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="33e64-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="33e64-130">Om du vill köra ditt nya Q#-program från Python sparar du följande kod som `host.py`:</span><span class="sxs-lookup"><span data-stu-id="33e64-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="33e64-131">Du kan sedan köra Python-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="33e64-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="33e64-132">C# med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="33e64-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="33e64-133">Om du vill köra ditt nya Q#-program från C# ändrar du `Driver.cs` så att följande C#-kod ingår:</span><span class="sxs-lookup"><span data-stu-id="33e64-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="33e64-134">Du kan sedan köra C#-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="33e64-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="33e64-135">C# med Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="33e64-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="33e64-136">Om du vill köra ditt nya Q#-program från C# i Visual Studio ändrar du `Driver.cs` så att följande C#-kod ingår:</span><span class="sxs-lookup"><span data-stu-id="33e64-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="33e64-137">Därefter trycker du på F5. Programmet startas och ett nytt fönster med följande resultat visas:</span><span class="sxs-lookup"><span data-stu-id="33e64-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="33e64-138">Åtgärden `ReflectAboutMarked` anropades bara fyra gånger, men ditt Q#-program hittade indatan ”01010” bland $2^{5} = 32$ möjliga indata!</span><span class="sxs-lookup"><span data-stu-id="33e64-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="33e64-139">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="33e64-139">Next steps</span></span>

<span data-ttu-id="33e64-140">Om du gillade den här snabbstarten kan du titta närmare på några av resurserna nedan, där du lär dig mer om hur du kan använda Q# för att skriva egna kvantprogram:</span><span class="sxs-lookup"><span data-stu-id="33e64-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="33e64-141">Tillbaka till guiden Komma igång med QDK</span><span class="sxs-lookup"><span data-stu-id="33e64-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="33e64-142">Prova en mer allmän Grover-sökalgoritm [exempel](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="33e64-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="33e64-143">Läs mer om Grovers sökning med Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="33e64-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="33e64-144">Läs mer om [Amplitudförstärkning](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), kvantberäkningstekniken bakom Grovers sökalgoritm</span><span class="sxs-lookup"><span data-stu-id="33e64-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="33e64-145">Begrepp inom kvantberäkning</span><span class="sxs-lookup"><span data-stu-id="33e64-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="33e64-146">Quantum Development Kit-exempel</span><span class="sxs-lookup"><span data-stu-id="33e64-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
