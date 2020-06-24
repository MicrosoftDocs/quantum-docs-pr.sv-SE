---
title: Utforska sammanflätning med Q#
description: Lär dig hur man skriver ett kvantprogram i Q#. Utveckla ett Bell-tillståndsprogram med Quantum Development Kit (QDK)
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 294366b884da93f11c60cfdbdce9b40cf5202b0d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275310"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="58a01-104">Självstudier: Utforska sammanflätning med Q\#</span><span class="sxs-lookup"><span data-stu-id="58a01-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="58a01-105">I den här självstudien visar vi hur du skriver ett Q#-program som ändrar och mäter kvantbitar samt visar effekterna av superposition och sammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="58a01-106">Du får hjälp med att installera QDK, skapa programmet och köra programmet på en kvantsimulator.</span><span class="sxs-lookup"><span data-stu-id="58a01-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="58a01-107">Du kommer att skriva ett program med namnet Bell som visar kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="58a01-108">Namnet Bell syftar på Bell-tillstånd, vilket är specifika kvanttillstånd för två kvantbitar som används för att visa de enklaste exemplen på superposition och kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58a01-109">Krav</span><span class="sxs-lookup"><span data-stu-id="58a01-109">Prerequisites</span></span>

<span data-ttu-id="58a01-110">Om du är redo att börja koda följer du nedanstående steg innan du fortsätter:</span><span class="sxs-lookup"><span data-stu-id="58a01-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="58a01-111">Installera Quantum Development Kit för [Python](xref:microsoft.quantum.install.python) eller [.NET](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="58a01-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="58a01-112">Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen</span><span class="sxs-lookup"><span data-stu-id="58a01-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="58a01-113">Du kan också följa med i texten utan att installera QDK. Du får då en översikt över Q#-programmeringsspråket och de första begreppen inom kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="58a01-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="58a01-114">Demonstrera kvantbitsbeteende med Q#</span><span class="sxs-lookup"><span data-stu-id="58a01-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="58a01-115">Kommer du ihåg vår enkla [definition av en kvantbit](xref:microsoft.quantum.overview.understanding)?</span><span class="sxs-lookup"><span data-stu-id="58a01-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="58a01-116">Medan klassiska bitar innehåller ett enda binärt värde, 0 eller 1, kan tillståndet för en [kvantbit](xref:microsoft.quantum.glossary#qubit) vara i en **superposition** med 0 och 1.</span><span class="sxs-lookup"><span data-stu-id="58a01-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="58a01-117">Begreppsmässigt kan man tänka på en kvantbit som en riktning (kallas även för vektor).</span><span class="sxs-lookup"><span data-stu-id="58a01-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="58a01-118">En kvantbit kan ha någon av de riktningar som är möjliga.</span><span class="sxs-lookup"><span data-stu-id="58a01-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="58a01-119">De två **klassiska tillstånden** är två riktningar. De motsvarar en chans på 100 % att mäta 0 och en chans på 100 % att mäta 1.</span><span class="sxs-lookup"><span data-stu-id="58a01-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="58a01-120">Detta kan även visualiseras med [Bloch-sfären](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="58a01-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="58a01-121">Mätningen genererar ett binärt resultat och ändrar kvantbitens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="58a01-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="58a01-122">Mätningen genererar ett binärt värde, antingen 0 eller 1.</span><span class="sxs-lookup"><span data-stu-id="58a01-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="58a01-123">Kvantbiten går från att vara i superposition (vilken riktning som helst) till ett av de klassiska tillstånden.</span><span class="sxs-lookup"><span data-stu-id="58a01-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="58a01-124">När du därefter upprepar samma mätning utan några andra åtgärder får du samma binära resultat.</span><span class="sxs-lookup"><span data-stu-id="58a01-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="58a01-125">Flera kvantbitar kan vara [**sammanflätade**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="58a01-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="58a01-126">När vi mäter en sammanflätad kvantbit får vi även veta de andra kvantbitarnas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="58a01-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="58a01-127">Nu är vi redo att demonstrera hur Q# uttrycker detta beteende.</span><span class="sxs-lookup"><span data-stu-id="58a01-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="58a01-128">Du börjar med det enklaste programmet och skapar det för att visa en kvantsuperposition och kvantsammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="58a01-129">Installation</span><span class="sxs-lookup"><span data-stu-id="58a01-129">Setup</span></span>

<span data-ttu-id="58a01-130">I den här självstudien används värdprogram. Den består av två delar:</span><span class="sxs-lookup"><span data-stu-id="58a01-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="58a01-131">En serie med kvantalgoritmer som implementeras med hjälp av kvantprogrammeringsspråket Q#.</span><span class="sxs-lookup"><span data-stu-id="58a01-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="58a01-132">Ett värdprogram som implementeras i antingen Python eller C#. Det fungerar som huvudstartpunkt och anropar Q#-åtgärder för att köra kvantalgoritmerna.</span><span class="sxs-lookup"><span data-stu-id="58a01-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="58a01-133">Python</span><span class="sxs-lookup"><span data-stu-id="58a01-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="58a01-134">Välj en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="58a01-134">Choose a location for your application</span></span>

1. <span data-ttu-id="58a01-135">Skapa en fil med namnet `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="58a01-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="58a01-136">Filen kommer att innehålla din Q#-kod.</span><span class="sxs-lookup"><span data-stu-id="58a01-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="58a01-137">Skapa en fil med namnet `host.py`.</span><span class="sxs-lookup"><span data-stu-id="58a01-137">Create a file called `host.py`.</span></span> <span data-ttu-id="58a01-138">Filen kommer att innehålla din Python-värdkod.</span><span class="sxs-lookup"><span data-stu-id="58a01-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a><span data-ttu-id="58a01-139">[C#-kommandorad](#tab/tabid-csharp).</span><span class="sxs-lookup"><span data-stu-id="58a01-139">[C# Command Line](#tab/tabid-csharp)</span></span>

1. <span data-ttu-id="58a01-140">Skapa ett nytt Q#-projekt:</span><span class="sxs-lookup"><span data-stu-id="58a01-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="58a01-141">Du bör se en `.csproj`-fil, en Q#-fil som heter `Operations.qs` och en värdprogramfil som heter `Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="58a01-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="58a01-142">Byt namn på Q#-filen</span><span class="sxs-lookup"><span data-stu-id="58a01-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="58a01-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58a01-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="58a01-144">Skapa ett nytt projekt</span><span class="sxs-lookup"><span data-stu-id="58a01-144">Create a new project</span></span>

   * <span data-ttu-id="58a01-145">Öppna Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58a01-145">Open Visual Studio</span></span>
   * <span data-ttu-id="58a01-146">Gå till menyn **Arkiv** och välj **Nytt** -> **Projekt...**</span><span class="sxs-lookup"><span data-stu-id="58a01-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="58a01-147">I projektmallens utforskare skriver du `Q#` i sökfältet och väljer mallen `Q# Application`</span><span class="sxs-lookup"><span data-stu-id="58a01-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="58a01-148">Ge ditt projekt namnet `Bell`</span><span class="sxs-lookup"><span data-stu-id="58a01-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="58a01-149">Byt namn på Q#-filen</span><span class="sxs-lookup"><span data-stu-id="58a01-149">Rename the Q# file</span></span>

   * <span data-ttu-id="58a01-150">Gå till **Solution Explorer**</span><span class="sxs-lookup"><span data-stu-id="58a01-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="58a01-151">Högerklicka på `Operations.qs`-filen</span><span class="sxs-lookup"><span data-stu-id="58a01-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="58a01-152">Byt namn på den till `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="58a01-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="58a01-153">Skriv en Q#-åtgärd</span><span class="sxs-lookup"><span data-stu-id="58a01-153">Write a Q# operation</span></span>

<span data-ttu-id="58a01-154">Vårt mål är att förbereda två kvantbitar i ett särskilt kvanttillstånd, demonstrera hur du använder kvantbitar med Q# för att ändra deras tillstånd, samt demonstrera effekterna av superposition och sammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="58a01-155">Vi kommer att bygga upp detta bit för bit för att visa kvantbitarnas tillstånd, åtgärder och mätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="58a01-156">**Översikt:**  I den första koden nedan visar vi dig hur man arbetar med kvantbitar i Q#.</span><span class="sxs-lookup"><span data-stu-id="58a01-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="58a01-157">Vi visar två åtgärder, `M` och `X`, som omvandlar tillståndet för en kvantbit.</span><span class="sxs-lookup"><span data-stu-id="58a01-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="58a01-158">I det här kodfragmentet definieras åtgärden `Set` som använder en parameter som kvantbit och en annan parameter, `desired`, som representerar det tillstånd som vi vill att kvantbiten ska ha.</span><span class="sxs-lookup"><span data-stu-id="58a01-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="58a01-159">Åtgärden `Set` utför en mätning på kvantbiten med åtgärden `M`.</span><span class="sxs-lookup"><span data-stu-id="58a01-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="58a01-160">I Q# returnerar en kvantbitsmätning alltid antingen `Zero` eller `One`.</span><span class="sxs-lookup"><span data-stu-id="58a01-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="58a01-161">Om mätningen returnerar ett värde som inte är lika med det önskade värdet, anger du att kvantbiten ska ”vändas”. Det innebär att den kör en `X`-åtgärd som ändrar kvantbitens tillstånd till ett nytt tillstånd där sannolikheten för att en mätning ska returnera `Zero` och `One` är omvänd.</span><span class="sxs-lookup"><span data-stu-id="58a01-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="58a01-162">En `TestBellState`-åtgärd läggs till för att demonstrera resultatet av åtgärden `Set`.</span><span class="sxs-lookup"><span data-stu-id="58a01-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="58a01-163">Den här åtgärden tar `Zero` eller `One` som indata och anropar `Set`-åtgärden ett visst antal gånger med indatan. Därefter räknas det antal gånger som `Zero` returnerades från kvantbitsmätningen och antalet gånger som `One` returnerades.</span><span class="sxs-lookup"><span data-stu-id="58a01-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="58a01-164">I den här första simuleringen av `TestBellState`-åtgärden förväntar vi oss givetvis att utdatan ska visa att alla mätningar av kvantbitsuppsättningen med `Zero` som parameterindata ska returnera `Zero`, och att alla mätningar av en kvantbitsuppsättning med `One` som parameterindata ska returnera `One`.</span><span class="sxs-lookup"><span data-stu-id="58a01-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="58a01-165">Senare kommer vi att lägga till kod i `TestBellState` som demonstrerar superposition och sammanflätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="58a01-166">Q#-åtgärdskod</span><span class="sxs-lookup"><span data-stu-id="58a01-166">Q# operation code</span></span>

1. <span data-ttu-id="58a01-167">Ersätt innehållet i filen Bells.qs med följande kod:</span><span class="sxs-lookup"><span data-stu-id="58a01-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="58a01-168">Den här åtgärden kan nu anropas för att försätta en kvantbit i ett klassiskt tillstånd som antingen returnerar `Zero` 100 % av tiden eller `One` 100 % av tiden.</span><span class="sxs-lookup"><span data-stu-id="58a01-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="58a01-169">`Zero` och `One` är konstanter som representerar de enda två möjliga resultaten från en kvantbitsmätning.</span><span class="sxs-lookup"><span data-stu-id="58a01-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="58a01-170">Åtgärden `Set` mäter kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="58a01-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="58a01-171">Om kvantbiten är i det tillstånd som vi vill ha, lämnar `Set` den oförändrad. Annars ändrar vi kvantbitens tillstånd till önskat tillstånd genom att köra åtgärden `X`.</span><span class="sxs-lookup"><span data-stu-id="58a01-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="58a01-172">Om Q#-åtgärder</span><span class="sxs-lookup"><span data-stu-id="58a01-172">About Q# operations</span></span>

<span data-ttu-id="58a01-173">En Q#-åtgärd är en kvantsubrutin.</span><span class="sxs-lookup"><span data-stu-id="58a01-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="58a01-174">Det innebär att det är en anropningsbar rutin som innehåller kvantåtgärder.</span><span class="sxs-lookup"><span data-stu-id="58a01-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="58a01-175">Argumenten i en åtgärd anges som en tuppel inom parentes.</span><span class="sxs-lookup"><span data-stu-id="58a01-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="58a01-176">Returtypen för åtgärden anges efter ett kolon.</span><span class="sxs-lookup"><span data-stu-id="58a01-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="58a01-177">I det här fallet saknar `Set`-åtgärden en retur, så den markeras som en retur för `Unit`.</span><span class="sxs-lookup"><span data-stu-id="58a01-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="58a01-178">Detta är Q#-motsvarigheten till `unit` i F#, vilket är ungefär detsamma som `void` i C# och en tom tuppel (`Tuple[()]`) i Python.</span><span class="sxs-lookup"><span data-stu-id="58a01-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="58a01-179">Du använde två kvantåtgärder i din första Q#-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="58a01-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="58a01-180">[M](xref:microsoft.quantum.intrinsic.m)-åtgärden som mäter kvantbitens tillstånd</span><span class="sxs-lookup"><span data-stu-id="58a01-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="58a01-181">[X](xref:microsoft.quantum.intrinsic.x)-åtgärden som vänder kvantbitens tillstånd</span><span class="sxs-lookup"><span data-stu-id="58a01-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="58a01-182">En kvantåtgärd omvandlar tillståndet för en kvantbit.</span><span class="sxs-lookup"><span data-stu-id="58a01-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="58a01-183">Ibland pratar man om kvantgrindar i stället för åtgärder, vilket motsvarar klassiska logiska grindar.</span><span class="sxs-lookup"><span data-stu-id="58a01-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="58a01-184">Detta kommer från när man började använda kvantberäkning och algoritmerna bara var en teoretisk konstruktion som visualiserades som diagram, liknande kretsdiagram i klassisk databehandling.</span><span class="sxs-lookup"><span data-stu-id="58a01-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="58a01-185">Lägg till testkod för Q#</span><span class="sxs-lookup"><span data-stu-id="58a01-185">Add Q# test code</span></span>

1. <span data-ttu-id="58a01-186">Lägg till följande åtgärd i `Bell.qs`-filen (inuti namnområdet) efter att `Set`-åtgärden har slutförts:</span><span class="sxs-lookup"><span data-stu-id="58a01-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="58a01-187">Åtgärden (`TestBellState`) kommer att upprepas för `count` iterationer, ange ett angivet `initial`-värde för en kvantbit och sedan mäta (`M`) resultatet.</span><span class="sxs-lookup"><span data-stu-id="58a01-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="58a01-188">Den samlar in statistik om hur många nollor och ettor som vi har mätt och returnerar dem till anroparen.</span><span class="sxs-lookup"><span data-stu-id="58a01-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="58a01-189">Den utför även en annan åtgärd som krävs.</span><span class="sxs-lookup"><span data-stu-id="58a01-189">It performs one other necessary operation.</span></span> <span data-ttu-id="58a01-190">Den återställer kvantbiten till ett känt tillstånd (`Zero`) innan den returnerar, så att andra kan allokera kvantbiten i ett känt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="58a01-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="58a01-191">Detta krävs av `using`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="58a01-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="58a01-192">Om variabler i Q#</span><span class="sxs-lookup"><span data-stu-id="58a01-192">About variables in Q#</span></span>

<span data-ttu-id="58a01-193">Som standard är variablerna i Q# oföränderliga. Värdet kan inte ändras efter att de har bundits.</span><span class="sxs-lookup"><span data-stu-id="58a01-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="58a01-194">Nyckelordet `let` används för att ange bindningen för en oföränderlig variabel.</span><span class="sxs-lookup"><span data-stu-id="58a01-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="58a01-195">Åtgärdsargument är alltid oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="58a01-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="58a01-196">Om du behöver en variabel vars värde kan ändras, till exempel `numOnes` i exemplet, kan du deklarera variabeln med nyckelordet `mutable`.</span><span class="sxs-lookup"><span data-stu-id="58a01-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="58a01-197">Ett värde för en föränderlig variabel kan ändras med hjälp av en `set`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="58a01-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="58a01-198">I båda fallen härleds variabeltypen av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="58a01-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="58a01-199">Q# kräver inte någon typanteckning för variabler.</span><span class="sxs-lookup"><span data-stu-id="58a01-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="58a01-200">Om `using`-instruktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="58a01-200">About `using` statements in Q#</span></span>

<span data-ttu-id="58a01-201">`using`-instruktionen är också unik för Q#.</span><span class="sxs-lookup"><span data-stu-id="58a01-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="58a01-202">Den används till att allokera kvantbitar som ska användas i ett kodblock.</span><span class="sxs-lookup"><span data-stu-id="58a01-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="58a01-203">I Q# allokeras och frigörs alla kvantbitar dynamiskt, i stället för att vara fasta resurser som finns där under hela livslängden för en komplex algoritm.</span><span class="sxs-lookup"><span data-stu-id="58a01-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="58a01-204">En `using`-instruktion allokerar en uppsättning kvantbitar vid starten och frigör dem sedan i slutet av blocket.</span><span class="sxs-lookup"><span data-stu-id="58a01-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="58a01-205">Skapa värdprogramkoden</span><span class="sxs-lookup"><span data-stu-id="58a01-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="58a01-206">Python</span><span class="sxs-lookup"><span data-stu-id="58a01-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="58a01-207">Öppna filen `host.py` och lägg till följande kod:</span><span class="sxs-lookup"><span data-stu-id="58a01-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="58a01-208">C#</span><span class="sxs-lookup"><span data-stu-id="58a01-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="58a01-209">Ersätt innehållet i filen `Driver.cs` med följande kod:</span><span class="sxs-lookup"><span data-stu-id="58a01-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="58a01-210">Om värdprogramkoden</span><span class="sxs-lookup"><span data-stu-id="58a01-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="58a01-211">Python</span><span class="sxs-lookup"><span data-stu-id="58a01-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="58a01-212">Python-värdprogrammet består av tre delar:</span><span class="sxs-lookup"><span data-stu-id="58a01-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="58a01-213">Beräkna eventuella argument som krävs för kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="58a01-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="58a01-214">I exemplet är `count` ett fast värde på 1000 och `initial` är det ursprungliga värdet för kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="58a01-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="58a01-215">Kör kvantalgoritmen genom att anropa metoden `simulate()` i den importerade Q#-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="58a01-216">Bearbeta resultatet för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-216">Process the result of the operation.</span></span> <span data-ttu-id="58a01-217">I det här exemplet tar `res` emot resultatet av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="58a01-218">Här är resultatet en tuppel med antalet nollor (`num_zeros`) och antalet ettor (`num_ones`) som har mätts av simulatorn.</span><span class="sxs-lookup"><span data-stu-id="58a01-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="58a01-219">Vi dekonstruerar tuppeln för att få de två fälten och skriver ut resultatet.</span><span class="sxs-lookup"><span data-stu-id="58a01-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="58a01-220">C#</span><span class="sxs-lookup"><span data-stu-id="58a01-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="58a01-221">C#-värdprogrammet består av fyra delar:</span><span class="sxs-lookup"><span data-stu-id="58a01-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="58a01-222">Konstruera en kvantsimulator.</span><span class="sxs-lookup"><span data-stu-id="58a01-222">Construct a quantum simulator.</span></span> <span data-ttu-id="58a01-223">I exemplet är `qsim` simulatorn.</span><span class="sxs-lookup"><span data-stu-id="58a01-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="58a01-224">Beräkna eventuella argument som krävs för kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="58a01-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="58a01-225">I exemplet är `count` ett fast värde på 1000 och `initial` är det ursprungliga värdet för kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="58a01-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="58a01-226">Köra kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="58a01-226">Run the quantum algorithm.</span></span> <span data-ttu-id="58a01-227">Varje Q#-åtgärd genererar en C#-klass med samma namn.</span><span class="sxs-lookup"><span data-stu-id="58a01-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="58a01-228">Den här klassen innehåller en `Run`-metod som **asynkront** utför åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="58a01-229">Körningen är asynkron eftersom körningen på den faktiska maskinvaran kommer att vara asynkron.</span><span class="sxs-lookup"><span data-stu-id="58a01-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="58a01-230">Eftersom metoden `Run` är asynkron, hämtar vi egenskapen `Result`. Den blockerar körningen tills aktiviteten har slutförts och returnerar resultatet synkront.</span><span class="sxs-lookup"><span data-stu-id="58a01-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="58a01-231">Bearbeta resultatet av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-231">Process the result of the operation.</span></span> <span data-ttu-id="58a01-232">I det här exemplet tar `res` emot resultatet av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="58a01-233">Här är resultatet en tuppel med antalet nollor (`numZeros`) och antalet ettor (`numOnes`) som har mätts av simulatorn.</span><span class="sxs-lookup"><span data-stu-id="58a01-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="58a01-234">Detta returneras som en ValueTuple i C#.</span><span class="sxs-lookup"><span data-stu-id="58a01-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="58a01-235">Vi dekonstruerar tuppeln för att få de två fälten, skriver ut resultatet och väntar på en tangenttryckning.</span><span class="sxs-lookup"><span data-stu-id="58a01-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="58a01-236">Skapa och kör</span><span class="sxs-lookup"><span data-stu-id="58a01-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="58a01-237">Python</span><span class="sxs-lookup"><span data-stu-id="58a01-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="58a01-238">Kör följande kommando i terminalen:</span><span class="sxs-lookup"><span data-stu-id="58a01-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="58a01-239">Det här kommandot kör värdprogrammet, vilket simulerar Q#-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58a01-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="58a01-240">Resultatet bör vara:</span><span class="sxs-lookup"><span data-stu-id="58a01-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="58a01-241">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="58a01-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="58a01-242">Kör följande i terminalen:</span><span class="sxs-lookup"><span data-stu-id="58a01-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="58a01-243">Kommandot hämtar automatiskt alla nödvändiga paket, skapar programmet och kör det sedan på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="58a01-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="58a01-244">Du kan också trycka på **F1** för att öppna kommandopaletten och välja **Felsökning: Starta utan felsökning.**</span><span class="sxs-lookup"><span data-stu-id="58a01-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="58a01-245">Du kan uppmanas att skapa en ny ``launch.json``-fil som beskriver hur man startar programmet.</span><span class="sxs-lookup"><span data-stu-id="58a01-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="58a01-246">Standardvärdet ``launch.json`` fungerar bra för de flesta program.</span><span class="sxs-lookup"><span data-stu-id="58a01-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="58a01-247">Resultatet bör vara:</span><span class="sxs-lookup"><span data-stu-id="58a01-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="58a01-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58a01-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="58a01-249">Du behöver bara trycka på `F5` för att ditt program ska börja byggas och köras!</span><span class="sxs-lookup"><span data-stu-id="58a01-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="58a01-250">Resultatet bör vara:</span><span class="sxs-lookup"><span data-stu-id="58a01-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="58a01-251">Programmet avslutas när du har tryckt på en tangent.</span><span class="sxs-lookup"><span data-stu-id="58a01-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="58a01-252">Förbered superposition</span><span class="sxs-lookup"><span data-stu-id="58a01-252">Prepare superposition</span></span>

<span data-ttu-id="58a01-253">**Översikt** Nu ska vi titta på hur Q# uttrycker de sätt som finns för att placera kvantbitar i superposition.</span><span class="sxs-lookup"><span data-stu-id="58a01-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="58a01-254">Kom ihåg att tillståndet för en kvantbit kan vara i en superposition på 0 och 1.</span><span class="sxs-lookup"><span data-stu-id="58a01-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="58a01-255">Vi använder `Hadamard`-åtgärden för att åstadkomma detta.</span><span class="sxs-lookup"><span data-stu-id="58a01-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="58a01-256">Om kvantbiten finns i något av de klassiska tillstånden (där en mätning alltid returnerar `Zero` eller `One`), kommer `Hadamard`- eller `H`-åtgärden att försätta kvantbiten i ett tillstånd där en mätning returnerar `Zero` 50 % av tiden och `One` 50 % av tiden.</span><span class="sxs-lookup"><span data-stu-id="58a01-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="58a01-257">Begreppsmässigt kan man tänka att kvantbiten är halvvägs mellan `Zero` och `One`.</span><span class="sxs-lookup"><span data-stu-id="58a01-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="58a01-258">När vi nu simulerar `TestBellState`-åtgärden ser vi att resultaten returnerar ungefär lika många `Zero` och `One` efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="58a01-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="58a01-259">Först försöker vi bara att vända kvantbiten (om den är i `Zero`-tillstånd kommer den att vändas till `One` och vice versa).</span><span class="sxs-lookup"><span data-stu-id="58a01-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="58a01-260">Detta görs genom att köra en `X`-åtgärd innan den mäts i `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="58a01-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="58a01-261">Resultatet blir omvänt (efter att du har tryckt på `F5`):</span><span class="sxs-lookup"><span data-stu-id="58a01-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="58a01-262">Men allt som vi har sett hittills är klassiskt.</span><span class="sxs-lookup"><span data-stu-id="58a01-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="58a01-263">Nu ska vi ha ett kvantresultat.</span><span class="sxs-lookup"><span data-stu-id="58a01-263">Let's get a quantum result.</span></span> <span data-ttu-id="58a01-264">Allt vi behöver göra är att ersätta `X`-åtgärden i föregående körning med en `H`- eller Hadamard-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="58a01-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="58a01-265">I stället för att vända kvantbiten hela vägen från 0 till 1, vänder vi bara den halvvägs.</span><span class="sxs-lookup"><span data-stu-id="58a01-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="58a01-266">De ersatta raderna i `TestBellState` ser nu ut så här:</span><span class="sxs-lookup"><span data-stu-id="58a01-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="58a01-267">Nu blir resultatet mer intressant:</span><span class="sxs-lookup"><span data-stu-id="58a01-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="58a01-268">Varje gång vi mäter ber vi om ett klassiskt värde, men kvantbiten är halvvägs mellan 0 och 1, så vi får (statistiskt sett) 0 halva tiden och 1 halva tiden.</span><span class="sxs-lookup"><span data-stu-id="58a01-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="58a01-269">Detta kallas för __superposition__ och ger oss den första verkliga inblicken i ett kvanttillstånd.</span><span class="sxs-lookup"><span data-stu-id="58a01-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="58a01-270">Förbereda sammanflätning</span><span class="sxs-lookup"><span data-stu-id="58a01-270">Prepare entanglement</span></span>

<span data-ttu-id="58a01-271">**Översikt:**  Nu ska vi titta på hur Q# uttrycker de sätt som finns för att sammanfläta kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="58a01-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="58a01-272">Först försätter vi den första kvantbiten i det ursprungliga tillståndet och sedan använder vi `H`-åtgärden för att placera den i superposition.</span><span class="sxs-lookup"><span data-stu-id="58a01-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="58a01-273">Innan vi mäter den första kvantbiten använder vi en ny åtgärd (`CNOT`), som står för Controlled-Not.</span><span class="sxs-lookup"><span data-stu-id="58a01-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="58a01-274">Resultatet när vi har kört åtgärden på två kvantbitar är att vända den andra kvantbiten om den första kvantbiten är `One`.</span><span class="sxs-lookup"><span data-stu-id="58a01-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="58a01-275">Nu är de två kvantbitarna sammanflätade.</span><span class="sxs-lookup"><span data-stu-id="58a01-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="58a01-276">Vår statistik för den första kvantbiten har inte ändrats (50/50 möjlighet för `Zero` eller `One` efter mätningen), men när vi nu mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="58a01-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="58a01-277">Vår `CNOT` har sammanflätat de två kvantbitarna, vilket innebär att det som händer med en av dem händer även för den andra.</span><span class="sxs-lookup"><span data-stu-id="58a01-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="58a01-278">Om du skulle omvända mätningarna (den andra kvantbiten före den första), skulle samma sak inträffa.</span><span class="sxs-lookup"><span data-stu-id="58a01-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="58a01-279">Det första måttet blir slumpmässigt och det andra blir låst med det värde som identifierades för den första mätningen.</span><span class="sxs-lookup"><span data-stu-id="58a01-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="58a01-280">Det första vi måste göra är att allokera två kvantbitar i stället för en i `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="58a01-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="58a01-281">Detta innebär att vi kan lägga till en ny åtgärd (`CNOT`) innan vi mäter (`M`) i `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="58a01-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="58a01-282">Vi har lagt till en annan `Set`-åtgärd för att initiera den första kvantbiten, för att säkerställa att den alltid är i `Zero`-tillståndet när vi startar.</span><span class="sxs-lookup"><span data-stu-id="58a01-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="58a01-283">Vi måste också återställa den andra kvantbiten innan den frigörs.</span><span class="sxs-lookup"><span data-stu-id="58a01-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="58a01-284">Den fullständiga rutinen ser nu ut så här:</span><span class="sxs-lookup"><span data-stu-id="58a01-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="58a01-285">Om vi kör detta får vi exakt samma 50/50-resultat som vi fick tidigare.</span><span class="sxs-lookup"><span data-stu-id="58a01-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="58a01-286">Men vad vi är intresserade av är hur den andra kvantbiten reagerar på den första mätningen.</span><span class="sxs-lookup"><span data-stu-id="58a01-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="58a01-287">Vi kommer att lägga till denna statistik med en ny version av `TestBellState`-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="58a01-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

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
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="58a01-288">Det nya returvärdet (`agree`) registrerar varje gång mätningen av den första kvantbiten matchar mätningen av den andra kvantbiten.</span><span class="sxs-lookup"><span data-stu-id="58a01-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="58a01-289">Vi måste också uppdatera värdprogrammet på lämpligt sätt:</span><span class="sxs-lookup"><span data-stu-id="58a01-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="58a01-290">Python</span><span class="sxs-lookup"><span data-stu-id="58a01-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="58a01-291">C#</span><span class="sxs-lookup"><span data-stu-id="58a01-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="58a01-292">Nu när vi kör ser vi något fantastiskt:</span><span class="sxs-lookup"><span data-stu-id="58a01-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="58a01-293">Som vi visade i översikten har vår statistik för den första kvantbiten inte ändrats (50/50 möjlighet för 0 eller 1), men när vi mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten eftersom de är sammanflätade.</span><span class="sxs-lookup"><span data-stu-id="58a01-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="58a01-294">Grattis, du har skrivit ditt första kvantprogram!</span><span class="sxs-lookup"><span data-stu-id="58a01-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="58a01-295">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="58a01-295">Next steps</span></span>

<span data-ttu-id="58a01-296">Självstudien [Grovers sökning](xref:microsoft.quantum.quickstarts.search) visar hur du skapar och kör Grovers sökning, en av de mest populära kvantberäkningsalgoritmerna. Den är ett bra exempel på ett Q#-program som kan användas för att lösa verkliga problem med hjälp av kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="58a01-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="58a01-297">I [Kom igång med Quantum Development Kit](xref:microsoft.quantum.welcome) finns fler sätt att lära sig Q# och kvantprogrammering på.</span><span class="sxs-lookup"><span data-stu-id="58a01-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
