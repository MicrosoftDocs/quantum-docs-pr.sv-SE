---
title: 'Utforska entanglement med :::no-loc(Q#):::'
description: 'Lär dig hur du skriver ett Quantum-program i :::no-loc(Q#)::: . Utveckla ett Bell-tillståndsprogram med Quantum Development Kit (QDK)'
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691662"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="5ff02-104">Självstudier: Utforska sammanflätning med Q\#</span><span class="sxs-lookup"><span data-stu-id="5ff02-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="5ff02-105">I den här självstudien visar vi hur du skriver ett :::no-loc(Q#)::: program som manipulerar och mäter qubits och demonstrerar effekterna av superposition och entanglement.</span><span class="sxs-lookup"><span data-stu-id="5ff02-105">In this tutorial, we show you how to write a :::no-loc(Q#)::: program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="5ff02-106">Du kommer att skriva ett program med namnet Bell som visar kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="5ff02-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="5ff02-107">Namnet Bell syftar på Bell-tillstånd, vilket är specifika kvanttillstånd för två kvantbitar som används för att visa de enklaste exemplen på superposition och kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="5ff02-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5ff02-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5ff02-108">Pre-requisites</span></span>

<span data-ttu-id="5ff02-109">Om du är redo att börja koda följer du nedanstående steg innan du fortsätter:</span><span class="sxs-lookup"><span data-stu-id="5ff02-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="5ff02-110">[Installera](xref:microsoft.quantum.install) Quantum Development Kit med din önskade språk-och utvecklings miljö.</span><span class="sxs-lookup"><span data-stu-id="5ff02-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="5ff02-111">Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen</span><span class="sxs-lookup"><span data-stu-id="5ff02-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="5ff02-112">Du kan också följa med i beräkningen utan att installera QDK, granska övervisningen av :::no-loc(Q#)::: programmeringsspråket och de första koncepten med Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="5ff02-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the :::no-loc(Q#)::: programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="5ff02-113">I den här självstudien får du lära dig att:</span><span class="sxs-lookup"><span data-stu-id="5ff02-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5ff02-114">Skapa och kombinera åtgärder i Q\#</span><span class="sxs-lookup"><span data-stu-id="5ff02-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="5ff02-115">Skapa åtgärder för att placera qubits i superposition, entangle och mät dem.</span><span class="sxs-lookup"><span data-stu-id="5ff02-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="5ff02-116">Demonstrera Quantum entanglement med ett :::no-loc(Q#)::: program som körs i en simulator.</span><span class="sxs-lookup"><span data-stu-id="5ff02-116">Demonstrate quantum entanglement with a :::no-loc(Q#)::: program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="5ff02-117">Demonstrera qubit-beteende med QDK</span><span class="sxs-lookup"><span data-stu-id="5ff02-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="5ff02-118">Medan klassiska bitar innehåller ett enda binärt värde, 0 eller 1, kan tillståndet för en [kvantbit](xref:microsoft.quantum.glossary#qubit) vara i en **superposition** med 0 och 1.</span><span class="sxs-lookup"><span data-stu-id="5ff02-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="5ff02-119">En qubit kan till exempel betraktas som en riktning i ett abstrakt utrymme (kallas även Vector).</span><span class="sxs-lookup"><span data-stu-id="5ff02-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="5ff02-120">Ett qubit-tillstånd kan vara i alla möjliga riktningar.</span><span class="sxs-lookup"><span data-stu-id="5ff02-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="5ff02-121">De två **klassiska tillstånden** är två riktningar. De motsvarar en chans på 100 % att mäta 0 och en chans på 100 % att mäta 1.</span><span class="sxs-lookup"><span data-stu-id="5ff02-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="5ff02-122">Mätningen genererar ett binärt resultat och ändrar kvantbitens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="5ff02-123">Måttet genererar ett binärt värde, antingen 0 eller 1.</span><span class="sxs-lookup"><span data-stu-id="5ff02-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="5ff02-124">Kvantbiten går från att vara i superposition (vilken riktning som helst) till ett av de klassiska tillstånden.</span><span class="sxs-lookup"><span data-stu-id="5ff02-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="5ff02-125">När du därefter upprepar samma mätning utan några andra åtgärder får du samma binära resultat.</span><span class="sxs-lookup"><span data-stu-id="5ff02-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="5ff02-126">Flera kvantbitar kan vara [**sammanflätade**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="5ff02-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="5ff02-127">När vi mäter en sammanflätad kvantbit får vi även veta de andra kvantbitarnas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="5ff02-128">Nu är vi redo att demonstrera hur :::no-loc(Q#)::: uttrycker det här beteendet.</span><span class="sxs-lookup"><span data-stu-id="5ff02-128">Now, we're ready to demonstrate how :::no-loc(Q#)::: expresses this behavior.</span></span>  <span data-ttu-id="5ff02-129">Du börjar med det enklaste programmet och skapar det för att visa en kvantsuperposition och kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="5ff02-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="5ff02-130">Skapa ett :::no-loc(Q#)::: projekt</span><span class="sxs-lookup"><span data-stu-id="5ff02-130">Creating a :::no-loc(Q#)::: project</span></span>

<span data-ttu-id="5ff02-131">Det första vi behöver göra är att skapa ett nytt :::no-loc(Q#)::: projekt.</span><span class="sxs-lookup"><span data-stu-id="5ff02-131">The first thing we have to do is to create a new :::no-loc(Q#)::: project.</span></span> <span data-ttu-id="5ff02-132">I den här självstudien kommer vi att använda miljön baserat på [ :::no-loc(Q#)::: program med vs Code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="5ff02-132">In this tutorial we are going to use the environment based on [:::no-loc(Q#)::: applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="5ff02-133">Så här skapar du ett nytt projekt i VS Code:</span><span class="sxs-lookup"><span data-stu-id="5ff02-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="5ff02-134">Klicka på **Visa** -> **Kommandopalett** och välj **:::no-loc(Q#):::: Skapa nytt projekt** .</span><span class="sxs-lookup"><span data-stu-id="5ff02-134">Click **View** -> **Command Palette** and select **:::no-loc(Q#):::: Create New Project** .</span></span>
2. <span data-ttu-id="5ff02-135">Klicka på **Fristående konsolprogram** .</span><span class="sxs-lookup"><span data-stu-id="5ff02-135">Click **Standalone console application** .</span></span>
3. <span data-ttu-id="5ff02-136">Gå till platsen där du vill spara projektet och klicka på **Skapa projekt** .</span><span class="sxs-lookup"><span data-stu-id="5ff02-136">Navigate to the location to save the project and click **Create Project** .</span></span>
4. <span data-ttu-id="5ff02-137">När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="5ff02-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="5ff02-138">I det här fallet kallas vi för projektet `Bell` .</span><span class="sxs-lookup"><span data-stu-id="5ff02-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="5ff02-139">Detta genererar två filer: `Bell.csproj` , projekt filen och `Program.qs` en mall för ett :::no-loc(Q#)::: program som vi ska använda för att skriva vårt program.</span><span class="sxs-lookup"><span data-stu-id="5ff02-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a :::no-loc(Q#)::: application that we will use to write our application.</span></span> <span data-ttu-id="5ff02-140">Innehållet i `Program.qs` ska vara:</span><span class="sxs-lookup"><span data-stu-id="5ff02-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="5ff02-141">Skriv Q- \# programmet</span><span class="sxs-lookup"><span data-stu-id="5ff02-141">Write the Q\# application</span></span>
 
<span data-ttu-id="5ff02-142">Vårt mål är att förbereda två qubits i ett särskilt Quantum-tillstånd som visar hur du kan arbeta med qubits med :::no-loc(Q#)::: för att ändra deras tillstånd och demonstrera effekterna av superposition och entanglement.</span><span class="sxs-lookup"><span data-stu-id="5ff02-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with :::no-loc(Q#)::: to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="5ff02-143">Vi bygger upp den här delen av en del för att presentera qubit-tillstånd,-åtgärder och-mått.</span><span class="sxs-lookup"><span data-stu-id="5ff02-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="5ff02-144">Initiera qubit med hjälp av mått</span><span class="sxs-lookup"><span data-stu-id="5ff02-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="5ff02-145">I det första kodfragmentet nedan visar vi dig hur du arbetar med qubits i :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="5ff02-145">In the first code snippet below, we show you how to work with qubits in :::no-loc(Q#):::.</span></span>  <span data-ttu-id="5ff02-146">Vi introducerar två åtgärder [`M`](xref:Microsoft.Quantum.Intrinsic.m) och [`X`](xref:Microsoft.Quantum.Intrinsic.X) som transformerar statusen för en qubit.</span><span class="sxs-lookup"><span data-stu-id="5ff02-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.m) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="5ff02-147">I det här kodfragmentet definieras åtgärden `SetQubitState` som använder en parameter som kvantbit och en annan parameter, `desired`, som representerar det tillstånd som vi vill att kvantbiten ska ha.</span><span class="sxs-lookup"><span data-stu-id="5ff02-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="5ff02-148">Åtgärden `SetQubitState` utför en mätning på kvantbiten med åtgärden `M`.</span><span class="sxs-lookup"><span data-stu-id="5ff02-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="5ff02-149">I :::no-loc(Q#)::: returnerar en qubit-mätning alltid antingen `Zero` eller `One` .</span><span class="sxs-lookup"><span data-stu-id="5ff02-149">In :::no-loc(Q#):::, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="5ff02-150">Om mätningen returnerar ett värde som inte är lika med det önskade värdet, `SetQubitState` "vänder" qubit; som är, kör den en `X` åtgärd som ändrar qubit-tillstånd till ett nytt tillstånd där sannolikheten för en mätning returneras `Zero` och `One` blir omvänd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="5ff02-151">På så sätt `SetQubitState` placeras alltid mål qubit i önskat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="5ff02-152">Ersätt innehållet i `Program.qs` med följande kod:</span><span class="sxs-lookup"><span data-stu-id="5ff02-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="5ff02-153">Den här åtgärden kan nu anropas för att försätta en kvantbit i ett klassiskt tillstånd som antingen returnerar `Zero` 100 % av tiden eller `One` 100 % av tiden.</span><span class="sxs-lookup"><span data-stu-id="5ff02-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="5ff02-154">`Zero` och `One` är konstanter som representerar de enda två möjliga resultaten från en kvantbitsmätning.</span><span class="sxs-lookup"><span data-stu-id="5ff02-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="5ff02-155">Åtgärden `SetQubitState` mäter kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="5ff02-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="5ff02-156">Om qubit är i det tillstånd som vi vill ha, `SetQubitState` lämnar du den ensamma. annars `X` ändrar vi qubit-statusen till önskat tillstånd genom att köra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5ff02-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="5ff02-157">Om :::no-loc(Q#)::: åtgärder</span><span class="sxs-lookup"><span data-stu-id="5ff02-157">About :::no-loc(Q#)::: operations</span></span>

<span data-ttu-id="5ff02-158">En :::no-loc(Q#)::: åtgärd är en Quantum-underrutin.</span><span class="sxs-lookup"><span data-stu-id="5ff02-158">A :::no-loc(Q#)::: operation is a quantum subroutine.</span></span> <span data-ttu-id="5ff02-159">Det vill säga att det är en rutin som kan anropas och som innehåller anrop till andra Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5ff02-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="5ff02-160">Argumenten i en åtgärd anges som en tuppel inom parentes.</span><span class="sxs-lookup"><span data-stu-id="5ff02-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="5ff02-161">Returtypen för åtgärden anges efter ett kolon.</span><span class="sxs-lookup"><span data-stu-id="5ff02-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="5ff02-162">I det här fallet `SetQubitState` har åtgärden ingen returtyp, så den markeras som retur `Unit` .</span><span class="sxs-lookup"><span data-stu-id="5ff02-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="5ff02-163">Detta är :::no-loc(Q#)::: detsamma `unit` som i F #, som är ungefär detsamma som `void` i C# och en tom tupel i python ( `()` som representeras av typ tipset `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="5ff02-163">This is the :::no-loc(Q#)::: equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="5ff02-164">Du har använt två Quantum-åtgärder i din första :::no-loc(Q#)::: åtgärd:</span><span class="sxs-lookup"><span data-stu-id="5ff02-164">You have used two quantum operations in your first :::no-loc(Q#)::: operation:</span></span>

* <span data-ttu-id="5ff02-165">[`M`](xref:Microsoft.Quantum.Intrinsic.m)Åtgärden, som mäter status för qubit</span><span class="sxs-lookup"><span data-stu-id="5ff02-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="5ff02-166">[`X`](xref:Microsoft.Quantum.Intrinsic.X)Åtgärden, som vänder sig till status för en qubit</span><span class="sxs-lookup"><span data-stu-id="5ff02-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="5ff02-167">En kvantåtgärd omvandlar tillståndet för en kvantbit.</span><span class="sxs-lookup"><span data-stu-id="5ff02-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="5ff02-168">Ibland pratar man om kvantgrindar i stället för åtgärder, vilket motsvarar klassiska logiska grindar.</span><span class="sxs-lookup"><span data-stu-id="5ff02-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="5ff02-169">Detta kommer från när man började använda kvantberäkning och algoritmerna bara var en teoretisk konstruktion som visualiserades som diagram, liknande kretsdiagram i klassisk databehandling.</span><span class="sxs-lookup"><span data-stu-id="5ff02-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="5ff02-170">Beräkning av mått resultat</span><span class="sxs-lookup"><span data-stu-id="5ff02-170">Counting measurement outcomes</span></span>

<span data-ttu-id="5ff02-171">En `TestBellState`-åtgärd läggs till för att demonstrera resultatet av åtgärden `SetQubitState`.</span><span class="sxs-lookup"><span data-stu-id="5ff02-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="5ff02-172">Den här åtgärden tar `Zero` eller `One` som indata och anropar `SetQubitState`-åtgärden ett visst antal gånger med indatan. Därefter räknas det antal gånger som `Zero` returnerades från kvantbitsmätningen och antalet gånger som `One` returnerades.</span><span class="sxs-lookup"><span data-stu-id="5ff02-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="5ff02-173">I den här första simuleringen av `TestBellState`-åtgärden förväntar vi oss givetvis att utdatan ska visa att alla mätningar av kvantbitsuppsättningen med `Zero` som parameterindata ska returnera `Zero`, och att alla mätningar av en kvantbitsuppsättning med `One` som parameterindata ska returnera `One`.</span><span class="sxs-lookup"><span data-stu-id="5ff02-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="5ff02-174">Vidare kommer vi att lägga till kod till `TestBellState` för att demonstrera överplacering och entanglement.</span><span class="sxs-lookup"><span data-stu-id="5ff02-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="5ff02-175">Lägg till följande åtgärd i `Program.qs`-filen (inuti namnområdet) efter att `SetQubitState`-åtgärden har slutförts:</span><span class="sxs-lookup"><span data-stu-id="5ff02-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="5ff02-176">Observera att vi har lagt till en rad innan `return` du skriver ut ett för klar ande meddelande i-konsolen med funktionen ( `Message` ) [Microsoft. Quantum. inneboende. Message]</span><span class="sxs-lookup"><span data-stu-id="5ff02-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="5ff02-177">Åtgärden (`TestBellState`) kommer att upprepas för `count` iterationer, ange ett angivet `initial`-värde för en kvantbit och sedan mäta (`M`) resultatet.</span><span class="sxs-lookup"><span data-stu-id="5ff02-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="5ff02-178">Den samlar in statistik om hur många nollor och ettor som vi har mätt och returnerar dem till anroparen.</span><span class="sxs-lookup"><span data-stu-id="5ff02-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="5ff02-179">Den utför även en annan åtgärd som krävs.</span><span class="sxs-lookup"><span data-stu-id="5ff02-179">It performs one other necessary operation.</span></span> <span data-ttu-id="5ff02-180">Den återställer kvantbiten till ett känt tillstånd (`Zero`) innan den returnerar, så att andra kan allokera kvantbiten i ett känt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="5ff02-181">Detta krävs av `using`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="5ff02-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="5ff02-182">Om variabler i Q\#</span><span class="sxs-lookup"><span data-stu-id="5ff02-182">About variables in Q\#</span></span>

<span data-ttu-id="5ff02-183">Som standard är variabler i :::no-loc(Q#)::: inte oföränderliga. deras värde kan inte ändras efter att de har bundits.</span><span class="sxs-lookup"><span data-stu-id="5ff02-183">By default, variables in :::no-loc(Q#)::: are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="5ff02-184">Nyckelordet `let` används för att ange bindningen för en oföränderlig variabel.</span><span class="sxs-lookup"><span data-stu-id="5ff02-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="5ff02-185">Åtgärdsargument är alltid oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="5ff02-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="5ff02-186">Om du behöver en variabel vars värde kan ändras, till exempel `numOnes` i exemplet, kan du deklarera variabeln med nyckelordet `mutable`.</span><span class="sxs-lookup"><span data-stu-id="5ff02-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="5ff02-187">Ett värde för en föränderlig variabel kan ändras med hjälp av en `set`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="5ff02-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="5ff02-188">I båda fallen härleds variabeltypen av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="5ff02-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="5ff02-189">:::no-loc(Q#)::: kräver inte någon typ av kommentarer för variabler.</span><span class="sxs-lookup"><span data-stu-id="5ff02-189">:::no-loc(Q#)::: doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="5ff02-190">Om `using` instruktioner i Q\#</span><span class="sxs-lookup"><span data-stu-id="5ff02-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="5ff02-191">`using`Instruktionen är också speciell för :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="5ff02-191">The `using` statement is also special to :::no-loc(Q#):::.</span></span> <span data-ttu-id="5ff02-192">Den används till att allokera kvantbitar som ska användas i ett kodblock.</span><span class="sxs-lookup"><span data-stu-id="5ff02-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="5ff02-193">I :::no-loc(Q#)::: tilldelas alla qubits dynamiskt och frigörs, i stället för fasta resurser som är där under hela livs längden för en komplex algoritm.</span><span class="sxs-lookup"><span data-stu-id="5ff02-193">In :::no-loc(Q#):::, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="5ff02-194">En `using`-instruktion allokerar en uppsättning kvantbitar vid starten och frigör dem sedan i slutet av blocket.</span><span class="sxs-lookup"><span data-stu-id="5ff02-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="5ff02-195">Kör koden från kommando tolken</span><span class="sxs-lookup"><span data-stu-id="5ff02-195">Run the code from the command prompt</span></span>

<span data-ttu-id="5ff02-196">För att kunna köra koden måste vi ange vilken kompilator *som* kan anropas för att köra kommandot när vi tillhandahåller `dotnet run` kommandot.</span><span class="sxs-lookup"><span data-stu-id="5ff02-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="5ff02-197">Detta görs med en enkel ändring i :::no-loc(Q#)::: filen genom att lägga till en rad med `@EntryPoint()` direkt föregående anrop: `TestBellState` åtgärden i det här fallet.</span><span class="sxs-lookup"><span data-stu-id="5ff02-197">This is done with a simple change in the :::no-loc(Q#)::: file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="5ff02-198">Den fullständiga koden ska vara:</span><span class="sxs-lookup"><span data-stu-id="5ff02-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="5ff02-199">För att köra programmet måste vi ange `count` och `initial` argument från kommando tolken.</span><span class="sxs-lookup"><span data-stu-id="5ff02-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="5ff02-200">Vi väljer till exempel `count = 1000` och `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="5ff02-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="5ff02-201">Ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5ff02-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="5ff02-202">Och du bör Observera följande utdata:</span><span class="sxs-lookup"><span data-stu-id="5ff02-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="5ff02-203">Om du försöker med `initial = Zero` bör du följa:</span><span class="sxs-lookup"><span data-stu-id="5ff02-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="5ff02-204">Förbered superposition</span><span class="sxs-lookup"><span data-stu-id="5ff02-204">Prepare superposition</span></span>

<span data-ttu-id="5ff02-205">Nu ska vi titta på hur :::no-loc(Q#)::: uttrycker sätt att placera qubits i superposition.</span><span class="sxs-lookup"><span data-stu-id="5ff02-205">Now let’s look at how :::no-loc(Q#)::: expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="5ff02-206">Kom ihåg att tillståndet för en kvantbit kan vara i en superposition på 0 och 1.</span><span class="sxs-lookup"><span data-stu-id="5ff02-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="5ff02-207">Vi använder `Hadamard`-åtgärden för att åstadkomma detta.</span><span class="sxs-lookup"><span data-stu-id="5ff02-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="5ff02-208">Om kvantbiten finns i något av de klassiska tillstånden (där en mätning alltid returnerar `Zero` eller `One`), kommer `Hadamard`- eller `H`-åtgärden att försätta kvantbiten i ett tillstånd där en mätning returnerar `Zero` 50 % av tiden och `One` 50 % av tiden.</span><span class="sxs-lookup"><span data-stu-id="5ff02-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="5ff02-209">Begreppsmässigt kan man tänka att kvantbiten är halvvägs mellan `Zero` och `One`.</span><span class="sxs-lookup"><span data-stu-id="5ff02-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="5ff02-210">När vi nu simulerar `TestBellState`-åtgärden ser vi att resultaten returnerar ungefär lika många `Zero` och `One` efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="5ff02-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="5ff02-211">`X` vänder qubit-tillstånd</span><span class="sxs-lookup"><span data-stu-id="5ff02-211">`X` flips qubit state</span></span>

<span data-ttu-id="5ff02-212">Först försöker vi bara vända qubit (om qubit är i `Zero` läget vänder den till `One` och vice versa).</span><span class="sxs-lookup"><span data-stu-id="5ff02-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="5ff02-213">Detta görs genom att köra en `X`-åtgärd innan den mäts i `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="5ff02-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="5ff02-214">Nu återförs resultatet:</span><span class="sxs-lookup"><span data-stu-id="5ff02-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="5ff02-215">Nu ska vi utforska Quantum-egenskaperna för qubits.</span><span class="sxs-lookup"><span data-stu-id="5ff02-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="5ff02-216">`H` förbereder överplacering</span><span class="sxs-lookup"><span data-stu-id="5ff02-216">`H` prepares superposition</span></span>

<span data-ttu-id="5ff02-217">Allt vi behöver göra är att ersätta `X`-åtgärden i föregående körning med en `H`- eller Hadamard-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="5ff02-218">I stället för att vända kvantbiten hela vägen från 0 till 1, vänder vi bara den halvvägs.</span><span class="sxs-lookup"><span data-stu-id="5ff02-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="5ff02-219">De ersatta raderna i `TestBellState` ser nu ut så här:</span><span class="sxs-lookup"><span data-stu-id="5ff02-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="5ff02-220">Nu blir resultatet mer intressant:</span><span class="sxs-lookup"><span data-stu-id="5ff02-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="5ff02-221">Varje gång vi mäter ber vi om ett klassiskt värde, men kvantbiten är halvvägs mellan 0 och 1, så vi får (statistiskt sett) 0 halva tiden och 1 halva tiden.</span><span class="sxs-lookup"><span data-stu-id="5ff02-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="5ff02-222">Detta kallas för **superposition** och ger oss den första verkliga inblicken i ett kvanttillstånd.</span><span class="sxs-lookup"><span data-stu-id="5ff02-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="5ff02-223">Förbereda sammanflätning</span><span class="sxs-lookup"><span data-stu-id="5ff02-223">Prepare entanglement</span></span>

<span data-ttu-id="5ff02-224">Nu ska vi titta på hur :::no-loc(Q#)::: uttrycker sätt att entangle qubits.</span><span class="sxs-lookup"><span data-stu-id="5ff02-224">Now let’s look at how :::no-loc(Q#)::: expresses ways to entangle qubits.</span></span>
<span data-ttu-id="5ff02-225">Först försätter vi den första kvantbiten i det ursprungliga tillståndet och sedan använder vi `H`-åtgärden för att placera den i superposition.</span><span class="sxs-lookup"><span data-stu-id="5ff02-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="5ff02-226">Innan vi mäter den första qubit använder vi en ny åtgärd ( `CNOT` ), som står för *kontrollerad – inte* .</span><span class="sxs-lookup"><span data-stu-id="5ff02-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT* .</span></span>  <span data-ttu-id="5ff02-227">Resultatet av att köra den här åtgärden på två qubits är att vända den andra qubit om den första qubit är `One` .</span><span class="sxs-lookup"><span data-stu-id="5ff02-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="5ff02-228">Nu är de två kvantbitarna sammanflätade.</span><span class="sxs-lookup"><span data-stu-id="5ff02-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="5ff02-229">Vår statistik för den första kvantbiten har inte ändrats (50/50 möjlighet för `Zero` eller `One` efter mätningen), men när vi nu mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="5ff02-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="5ff02-230">Vår `CNOT` har sammanflätat de två kvantbitarna, vilket innebär att det som händer med en av dem händer även för den andra.</span><span class="sxs-lookup"><span data-stu-id="5ff02-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="5ff02-231">Om du skulle omvända mätningarna (den andra kvantbiten före den första), skulle samma sak inträffa.</span><span class="sxs-lookup"><span data-stu-id="5ff02-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="5ff02-232">Det första måttet blir slumpmässigt och det andra blir låst med det värde som identifierades för den första mätningen.</span><span class="sxs-lookup"><span data-stu-id="5ff02-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="5ff02-233">Det första vi behöver göra är att allokera två qubits i stället för en i `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="5ff02-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="5ff02-234">Detta innebär att vi kan lägga till en ny åtgärd (`CNOT`) innan vi mäter (`M`) i `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="5ff02-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="5ff02-235">Vi har lagt till en annan `SetQubitState`-åtgärd för att initiera den första kvantbiten, för att säkerställa att den alltid är i `Zero`-tillståndet när vi startar.</span><span class="sxs-lookup"><span data-stu-id="5ff02-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="5ff02-236">Vi måste också återställa den andra kvantbiten innan den frigörs.</span><span class="sxs-lookup"><span data-stu-id="5ff02-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="5ff02-237">Den fullständiga rutinen ser nu ut så här:</span><span class="sxs-lookup"><span data-stu-id="5ff02-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="5ff02-238">Om vi kör detta får vi exakt samma 50/50-resultat som vi fick tidigare.</span><span class="sxs-lookup"><span data-stu-id="5ff02-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="5ff02-239">Men vad vi är intresserade av är hur den andra kvantbiten reagerar på den första mätningen.</span><span class="sxs-lookup"><span data-stu-id="5ff02-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="5ff02-240">Vi kommer att lägga till denna statistik med en ny version av `TestBellState`-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="5ff02-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="5ff02-241">Det nya returvärdet (`agree`) registrerar varje gång mätningen av den första kvantbiten matchar mätningen av den andra kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="5ff02-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="5ff02-242">Kör koden som vi erhåller:</span><span class="sxs-lookup"><span data-stu-id="5ff02-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="5ff02-243">Som vi visade i översikten har vår statistik för den första kvantbiten inte ändrats (50/50 möjlighet för 0 eller 1), men när vi mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten eftersom de är sammanflätade.</span><span class="sxs-lookup"><span data-stu-id="5ff02-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ff02-244">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5ff02-244">Next steps</span></span>

<span data-ttu-id="5ff02-245">I självstudien om [Grover](xref:microsoft.quantum.quickstarts.search) får du lära dig hur du skapar och kör Grover search, en av de mest populära Quantum Computing-algoritmerna och erbjuder ett bra exempel på ett :::no-loc(Q#)::: program som kan användas för att lösa verkliga problem med Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="5ff02-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a :::no-loc(Q#)::: program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="5ff02-246">[Kom igång med Quantum Development Kit](xref:microsoft.quantum.welcome) rekommenderar fler sätt att lära sig :::no-loc(Q#)::: och Quantum-programmering.</span><span class="sxs-lookup"><span data-stu-id="5ff02-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn :::no-loc(Q#)::: and quantum programming.</span></span>
