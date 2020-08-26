---
title: Kör Grover Sök algoritm i Q# Quantum Development Kit
description: Bygg ett Q# projekt som demonstrerar Grover-algoritmen, en av de kanoniska Quantum-algoritmerna.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: f2ae56bdca893e8a317c16d0a993da15b9f021b5
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863111"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="1e06b-103">Självstudier: Implementera Grovers sökalgoritm i Q\#</span><span class="sxs-lookup"><span data-stu-id="1e06b-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="1e06b-104">I den här självstudien lär du dig att skapa och köra Grover-sökning som påskyndar sökningen i ostrukturerade data.</span><span class="sxs-lookup"><span data-stu-id="1e06b-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="1e06b-105">Grover: s sökning är en av de mest populära Quantum Computing-algoritmerna, och den här relativt små Q# implementeringen ger dig en uppfattning om några av fördelarna med programmering av Quantum-lösningar med ett högnivå Q# Quantum programmeringsspråk för att uttrycka Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="1e06b-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="1e06b-106">I slutet av guiden kommer du att se att simuleringen hittar en specifik sträng i listan med osorterade poster på en bråkdel av den tid det skulle ta att söka igenom hela listan på en klassisk dator.</span><span class="sxs-lookup"><span data-stu-id="1e06b-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="1e06b-107">Grovers algoritm söker i en lista med ostrukturerade data efter vissa objekt.</span><span class="sxs-lookup"><span data-stu-id="1e06b-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="1e06b-108">Den kan till exempel svara på frågan: Är det här kortet som drogs ur en kortlek hjärter ess?</span><span class="sxs-lookup"><span data-stu-id="1e06b-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="1e06b-109">Märkningen av det speciella objektet kallas för _markerad indata_.</span><span class="sxs-lookup"><span data-stu-id="1e06b-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="1e06b-110">Med hjälp av Grovers sökalgoritm kommer kvantdatorn garanterat att utföra sökningen i färre steg än antalet objekt i listan som du söker i, något som inte kan göras av en klassisk algoritm.</span><span class="sxs-lookup"><span data-stu-id="1e06b-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="1e06b-111">Den ökade hastigheten när en kortlek ska genomsökas är försumbar, men i listor som innehåller miljontals eller miljardtals objekt blir det mer viktigt.</span><span class="sxs-lookup"><span data-stu-id="1e06b-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="1e06b-112">Du kan bygga Grovers sökalgoritm med bara några rader kod.</span><span class="sxs-lookup"><span data-stu-id="1e06b-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e06b-113">Krav</span><span class="sxs-lookup"><span data-stu-id="1e06b-113">Prerequisites</span></span>

- <span data-ttu-id="1e06b-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="1e06b-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="1e06b-115">Vad gör Grovers sökalgoritm?</span><span class="sxs-lookup"><span data-stu-id="1e06b-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="1e06b-116">Grovers algoritm frågar om ett objekt i en lista är det som vi söker efter.</span><span class="sxs-lookup"><span data-stu-id="1e06b-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="1e06b-117">Detta görs genom att en kvantsuperposition skapas av indexen i listan med respektive koefficient, eller sannolikhetsamplitud, vilket utgör sannolikheten för att det aktuella indexet är det som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="1e06b-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="1e06b-118">Algoritmen består av två steg som ökar indexkoefficienten som vi söker efter inkrementellt, fram till att sannolikhetsamplituden för den aktuella koefficienten blir ett.</span><span class="sxs-lookup"><span data-stu-id="1e06b-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="1e06b-119">Antalet stegvisa ökningar är färre än antalet objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="1e06b-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="1e06b-120">Det här är anledningen till att Grovers sökalgoritm utför sökningen i färre steg än en klassisk algoritm.</span><span class="sxs-lookup"><span data-stu-id="1e06b-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Funktionsdiagram över Grovers sökalgoritm](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="1e06b-122">Skriva koden</span><span class="sxs-lookup"><span data-stu-id="1e06b-122">Write the code</span></span>

1. <span data-ttu-id="1e06b-123">[Skapa ett nytt Q# projekt för programmet](xref:microsoft.quantum.install.standalone)med hjälp av Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="1e06b-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="1e06b-124">Ge projektet rubriken `Grover`.</span><span class="sxs-lookup"><span data-stu-id="1e06b-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="1e06b-125">I projektfilen `Program.qs` lägger du till följande kod:</span><span class="sxs-lookup"><span data-stu-id="1e06b-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="1e06b-126">Definiera listan som vi söker i genom att skapa den nya filen `Reflections.qs` där du klistrar in följande kod:</span><span class="sxs-lookup"><span data-stu-id="1e06b-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="1e06b-127">Åtgärden `ReflectAboutMarked` definierar den markerade indata som du söker efter: Strängen med alternerande nollor och ettor.</span><span class="sxs-lookup"><span data-stu-id="1e06b-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="1e06b-128">I det här exemplet hårdkodas markerad indata, vilket kan utökas till att söka efter olika indata eller generaliseras för alla indata.</span><span class="sxs-lookup"><span data-stu-id="1e06b-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="1e06b-129">Kör sedan det nya Q# programmet för att hitta objektet som marker ATS av `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="1e06b-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="1e06b-130">Q# program med Visual Studio eller Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1e06b-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="1e06b-131">Den körbara filen kör åtgärden eller funktionen som har markerats med attributet `@EntryPoint()` i en simulator eller i ett resursuppskattningsverktyg, beroende på projektkonfigurationen och kommandoradsalternativen.</span><span class="sxs-lookup"><span data-stu-id="1e06b-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="1e06b-132">Tryck bara på Ctrl+F5 i Visual Studio för att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="1e06b-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="1e06b-133">Skapa `Program.qs` första gången genom att skriva följande i terminalfönstret i VS Code:</span><span class="sxs-lookup"><span data-stu-id="1e06b-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="1e06b-134">För efterföljande körningar behöver du inte bygga det igen.</span><span class="sxs-lookup"><span data-stu-id="1e06b-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="1e06b-135">Du kör det bara genom att skriva följande kommando och trycka på Retur:</span><span class="sxs-lookup"><span data-stu-id="1e06b-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="1e06b-136">Följande meddelande bör visas i terminalfönstret:</span><span class="sxs-lookup"><span data-stu-id="1e06b-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="1e06b-137">Det beror på att du inte angav hur många kvantbitar du ville använda. Därför visar terminalfönstret vilka kommandon som är tillgängliga för den körbara filen</span><span class="sxs-lookup"><span data-stu-id="1e06b-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="1e06b-138">Om vi vill använda fem kvantbitar skriver vi:</span><span class="sxs-lookup"><span data-stu-id="1e06b-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="1e06b-139">När du trycker på Retur bör du se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="1e06b-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="1e06b-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1e06b-140">Next steps</span></span>

<span data-ttu-id="1e06b-141">Om du gillade den här själv studie kursen kan du läsa mer om hur du kan använda Q# för att skriva egna Quantum-program på några av resurserna nedan.</span><span class="sxs-lookup"><span data-stu-id="1e06b-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="1e06b-142">Tillbaka till guiden Komma igång med QDK</span><span class="sxs-lookup"><span data-stu-id="1e06b-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="1e06b-143">Prova en mer allmän Grover-sökalgoritm [exempel](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="1e06b-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="1e06b-144">Läs mer om Grovers sökning med Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="1e06b-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="1e06b-145">Läs mer om [Amplitudförstärkning][amplitude-amplification], kvantberäkningstekniken bakom Grovers sökalgoritm</span><span class="sxs-lookup"><span data-stu-id="1e06b-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="1e06b-146">Begrepp inom kvantberäkning</span><span class="sxs-lookup"><span data-stu-id="1e06b-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="1e06b-147">Quantum Development Kit-exempel</span><span class="sxs-lookup"><span data-stu-id="1e06b-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
