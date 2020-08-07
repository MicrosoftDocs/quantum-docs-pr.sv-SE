---
title: Testa och felsöka
description: Lär dig hur du använder enhets tester, fakta och intyg och dumpa funktioner för att testa och felsöka Quantum-program.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2b5276da594ba263177d435c1153f6d96e29c4e8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867921"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="c4788-103">Testa och felsöka</span><span class="sxs-lookup"><span data-stu-id="c4788-103">Testing and debugging</span></span>

<span data-ttu-id="c4788-104">Precis som med klassisk programmering är det viktigt att kunna kontrol lera att Quantum-program fungerar som avsett och för att kunna diagnostisera felaktig funktion.</span><span class="sxs-lookup"><span data-stu-id="c4788-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="c4788-105">I det här avsnittet tar vi upp de verktyg som erbjuds av Q# för att testa och felsöka Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="c4788-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="c4788-106">Enhets tester</span><span class="sxs-lookup"><span data-stu-id="c4788-106">Unit Tests</span></span>

<span data-ttu-id="c4788-107">En vanlig metod för att testa klassiska program är att skriva små program som heter *enhets test*, som kör kod i ett bibliotek och jämför dess utdata med förväntade utdata.</span><span class="sxs-lookup"><span data-stu-id="c4788-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="c4788-108">Du kan till exempel se till att `Square(2)` returer `4` sedan du vet att du vet *en föregående* , $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="c4788-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="c4788-109">Q#har stöd för att skapa enhets tester för Quantum-program och som kan köras som tester i [xUnit](https://xunit.github.io/) unit test Framework.</span><span class="sxs-lookup"><span data-stu-id="c4788-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="c4788-110">Skapa ett test projekt</span><span class="sxs-lookup"><span data-stu-id="c4788-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c4788-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c4788-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c4788-112">Öppna Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c4788-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="c4788-113">Gå till **Arkiv** -menyn och välj **nytt > projekt.**... I det övre högra hörnet söker du efter `Q#` och väljer mallen \*\* Q# testa projekt\*\* .</span><span class="sxs-lookup"><span data-stu-id="c4788-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c4788-114">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4788-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c4788-115">Kör följande kommando från din favorit kommando rad:</span><span class="sxs-lookup"><span data-stu-id="c4788-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="c4788-116">Det nya projektet har en enda fil `Tests.qs` som ger en praktisk plats för att definiera nya Q# enhets test.</span><span class="sxs-lookup"><span data-stu-id="c4788-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="c4788-117">Den här filen innehåller en inlednings prov enhet `AllocateQubit` som kontrollerar att en nyligen allokerad qubit är i läget $ \ket {0} $ och skriver ut ett meddelande:</span><span class="sxs-lookup"><span data-stu-id="c4788-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="c4788-118">Varje Q# åtgärd eller funktion som tar ett argument av typen `Unit` och returer `Unit` kan markeras som ett enhets test via `@Test("...")` attributet.</span><span class="sxs-lookup"><span data-stu-id="c4788-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="c4788-119">I föregående exempel är argumentet till attributet, `"QuantumSimulator"` , anger målet som testet körs på.</span><span class="sxs-lookup"><span data-stu-id="c4788-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="c4788-120">Ett enda test kan köras på flera mål.</span><span class="sxs-lookup"><span data-stu-id="c4788-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="c4788-121">Du kan till exempel lägga till ett attribut `@Test("ResourcesEstimator")` före `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="c4788-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="c4788-122">Spara filen och kör alla tester.</span><span class="sxs-lookup"><span data-stu-id="c4788-122">Save the file and run all tests.</span></span> <span data-ttu-id="c4788-123">Det bör nu finnas två enhets test, en där `AllocateQubit` körs på `QuantumSimulator` och en där den körs i `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="c4788-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="c4788-124">Q#Kompilatorn känner igen de inbyggda målen `"QuantumSimulator"` , `"ToffoliSimulator"` och `"ResourcesEstimator"` som giltiga körnings mål för enhets tester.</span><span class="sxs-lookup"><span data-stu-id="c4788-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid execution targets for unit tests.</span></span> <span data-ttu-id="c4788-125">Det är också möjligt att ange ett fullständigt kvalificerat namn för att definiera ett anpassat körnings mål.</span><span class="sxs-lookup"><span data-stu-id="c4788-125">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="c4788-126">Köra Q# enhets tester</span><span class="sxs-lookup"><span data-stu-id="c4788-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c4788-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c4788-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c4788-128">Som en engångs inställning per lösning går du till **test** -menyn och väljer **test inställningar > standard processor arkitektur > x64**.</span><span class="sxs-lookup"><span data-stu-id="c4788-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="c4788-129">Standardinställning för processor arkitektur för Visual Studio lagras i lösnings alternativ ( `.suo` )-filen för varje lösning.</span><span class="sxs-lookup"><span data-stu-id="c4788-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="c4788-130">Om du tar bort den här filen måste du välja **x64** som processor arkitektur igen.</span><span class="sxs-lookup"><span data-stu-id="c4788-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="c4788-131">Skapa projektet, öppna **test** -menyn och välj **Windows > test Utforskaren**.</span><span class="sxs-lookup"><span data-stu-id="c4788-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="c4788-132">**AllocateQubit** visas i listan över tester i gruppen **inte körnings test** .</span><span class="sxs-lookup"><span data-stu-id="c4788-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="c4788-133">Välj **Kör alla** eller kör det här enskilda testet.</span><span class="sxs-lookup"><span data-stu-id="c4788-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c4788-134">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4788-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c4788-135">Om du vill köra tester navigerar du till projektmappen (mappen som innehåller `Tests.csproj` ) och kör kommandot:</span><span class="sxs-lookup"><span data-stu-id="c4788-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="c4788-136">Du bör få utdata som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="c4788-136">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="c4788-137">Enhets test kan filtreras efter namn eller körnings mål:</span><span class="sxs-lookup"><span data-stu-id="c4788-137">Unit tests can be filtered according to their name or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="c4788-138">Den inbyggda funktionen <xref:microsoft.quantum.intrinsic.message> har typ `(String -> Unit)` och gör det möjligt att skapa diagnostiska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c4788-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c4788-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c4788-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c4788-140">När du har kört ett test i test Utforskaren och klickar på testet visas en panel med information om testkörning: steg-/misslyckande status, förfluten tid och en länk till utdata.</span><span class="sxs-lookup"><span data-stu-id="c4788-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test execution: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="c4788-141">Klicka på **utdata** för att öppna test resultatet i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="c4788-141">Click **Output** to open the test output in a new window.</span></span>

![testa utdata](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c4788-143">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4788-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c4788-144">Status för pass/misslyckande för varje test skrivs ut till-konsolen av `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="c4788-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="c4788-145">Vid misslyckade tester skrivs utdata också ut till-konsolen för att hjälpa till att diagnostisera felet.</span><span class="sxs-lookup"><span data-stu-id="c4788-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="c4788-146">Fakta och intyg</span><span class="sxs-lookup"><span data-stu-id="c4788-146">Facts and Assertions</span></span>

<span data-ttu-id="c4788-147">Eftersom funktioner i Q# inte har några _logiska_ sid effekter kan du aldrig se, från ett Q# program, andra typer av effekter från att köra en funktion vars Utdatatyp är den tomma tuppeln `()` .</span><span class="sxs-lookup"><span data-stu-id="c4788-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="c4788-148">Det vill säga att mål datorn kan välja att inte köra någon funktion som returnerar `()` med garantin att detta utelämnande inte ändrar beteendet för någon av följande Q# koder.</span><span class="sxs-lookup"><span data-stu-id="c4788-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="c4788-149">Detta beteende gör att funktioner returnerar `()` (till exempel `Unit` ) ett användbart verktyg för att bädda in kontroller och fel söknings logik i Q# program.</span><span class="sxs-lookup"><span data-stu-id="c4788-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="c4788-150">Vi ska tänka på ett enkelt exempel:</span><span class="sxs-lookup"><span data-stu-id="c4788-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="c4788-151">Här anger nyckelordet `fail` att beräkningen inte ska fortsätta och genererar ett undantag på mål datorn som kör Q# programmet.</span><span class="sxs-lookup"><span data-stu-id="c4788-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="c4788-152">Efter definition kan ett problem av den här typen inte observeras inifrån Q# , eftersom mål datorn inte längre kör Q# koden efter att ha nått en `fail` instruktion.</span><span class="sxs-lookup"><span data-stu-id="c4788-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="c4788-153">Om vi fortsätter att gå förbi ett anrop till `PositivityFact` kan vi därför vara säker på att inaktuella inaktuella inkommer till positiv.</span><span class="sxs-lookup"><span data-stu-id="c4788-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="c4788-154">Observera att vi kan implementera samma beteende som att `PositivityFact` använda [`Fact`](xref:microsoft.quantum.diagnostics.fact) funktionen från <xref:microsoft.quantum.diagnostics> namn området:</span><span class="sxs-lookup"><span data-stu-id="c4788-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="c4788-155">*Kontroller*, å andra sidan, används på liknande sätt som fakta, men det kan bero på mål datorns tillstånd.</span><span class="sxs-lookup"><span data-stu-id="c4788-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="c4788-156">På motsvarande sätt definieras de som åtgärder, medan fakta definieras som funktioner (som i föregående exempel).</span><span class="sxs-lookup"><span data-stu-id="c4788-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="c4788-157">För att förstå skillnaden bör du överväga följande användning av ett faktum i en kontroll:</span><span class="sxs-lookup"><span data-stu-id="c4788-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="c4788-158">Här använder vi åtgärden <xref:microsoft.quantum.environment.getqubitsavailabletouse> för att returnera antalet qubits som kan användas.</span><span class="sxs-lookup"><span data-stu-id="c4788-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="c4788-159">Eftersom detta beror på programmets globala tillstånd och dess körnings miljö, `AssertQubitsAreAvailable` måste även vår definition vara en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c4788-159">As this depends on the global state of the program and its execution environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="c4788-160">Vi kan dock använda det globala läget för att ge ett enkelt `Bool` värde som inmatat för `Fact` funktionen.</span><span class="sxs-lookup"><span data-stu-id="c4788-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="c4788-161">[Inledning, som](xref:microsoft.quantum.libraries.standard.prelude)bygger på dessa idéer, erbjuder två särskilt användbara intyg <xref:microsoft.quantum.diagnostics.assertmeasurement> och <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> båda modellerade som-åtgärder på `()` .</span><span class="sxs-lookup"><span data-stu-id="c4788-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="c4788-162">Dessa intyg var och en tar en Pauli-operatör som beskriver en viss värdering av intresse, ett Quantum-register som en mätning utförs på och ett hypotetiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="c4788-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="c4788-163">Mål datorer som arbetar med simuleringen är inte kopplade till [någon-kloning-satsen](https://en.wikipedia.org/wiki/No-cloning_theorem)och kan utföra sådana mätningar utan att störa det register som skickas till sådana intyg.</span><span class="sxs-lookup"><span data-stu-id="c4788-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="c4788-164">En simulator kan sedan, som liknar `PositivityFact` funktionen föregående, stoppa beräkningen om det hypotetiska resultatet inte observeras i övningen:</span><span class="sxs-lookup"><span data-stu-id="c4788-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="c4788-165">På fysisk Quantum-maskinvara där ingen-kloning-satsen förhindrar granskning av ett Quantum-tillstånd, `AssertMeasurement` returnerar och fungerar de `AssertMeasurementProbability` bara utan `()` någon annan påverkan.</span><span class="sxs-lookup"><span data-stu-id="c4788-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="c4788-166"><xref:microsoft.quantum.diagnostics>Namn området innehåller flera fler funktioner i `Assert` serien, där du kan kontrol lera mer avancerade villkor.</span><span class="sxs-lookup"><span data-stu-id="c4788-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="c4788-167">Dumpa funktioner</span><span class="sxs-lookup"><span data-stu-id="c4788-167">Dump Functions</span></span>

<span data-ttu-id="c4788-168">För att hjälpa till att felsöka Quantum-program <xref:microsoft.quantum.diagnostics> innehåller namn området två funktioner som kan dumpa till en fil aktuella status för mål datorn: <xref:microsoft.quantum.diagnostics.dumpmachine> och <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="c4788-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="c4788-169">De utdata som genereras av var och en beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="c4788-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="c4788-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="c4788-170">DumpMachine</span></span>

<span data-ttu-id="c4788-171">Den fullständiga Quantum-simulatorn som distribueras som en del av Quantum Development Kit skriver till filen [Wave-funktionen](https://en.wikipedia.org/wiki/Wave_function) i hela Quantum-systemet, som en endimensionell matris med komplexa tal, där varje element representerar amplituden av sannolikheten för att mäta beräknings bas status $ \ket{n} $, där $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ för BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="c4788-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="c4788-172">Till exempel på en dator som bara har två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} genererar \end{align} $ $ anrop <xref:microsoft.quantum.diagnostics.dumpmachine> följande utdata:</span><span class="sxs-lookup"><span data-stu-id="c4788-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c4788-173">Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.</span><span class="sxs-lookup"><span data-stu-id="c4788-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="c4788-174">Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{n} $ i båda formaten kartesiska och Polar.</span><span class="sxs-lookup"><span data-stu-id="c4788-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="c4788-175">I detalj för den första raden:</span><span class="sxs-lookup"><span data-stu-id="c4788-175">In detail for the first row:</span></span>

* <span data-ttu-id="c4788-176">**`∣0❭:`** den här raden motsvarar `0` beräknings bas läget</span><span class="sxs-lookup"><span data-stu-id="c4788-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="c4788-177">**`0.707107 +  0.000000 i`**: sannolikheten amplitud i kartesiska-format.</span><span class="sxs-lookup"><span data-stu-id="c4788-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="c4788-178">**` == `**: `equal` tecknet separerar båda motsvarande representationer.</span><span class="sxs-lookup"><span data-stu-id="c4788-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="c4788-179">**`**********  `**: En grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta den här tillstånds vektorn.</span><span class="sxs-lookup"><span data-stu-id="c4788-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="c4788-180">**`[ 0.500000 ]`**: det numeriska värdet för storlek</span><span class="sxs-lookup"><span data-stu-id="c4788-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="c4788-181">**`    ---`**: En grafisk representation av amplitudens fas (se följande utdata).</span><span class="sxs-lookup"><span data-stu-id="c4788-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="c4788-182">**`[ 0.0000 rad ]`**: det numeriska värdet för fasen (i radianer).</span><span class="sxs-lookup"><span data-stu-id="c4788-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="c4788-183">Både storleken och fasen visas med en grafisk representation.</span><span class="sxs-lookup"><span data-stu-id="c4788-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="c4788-184">Representation av storlek är rakt framåt: det visar ett fält med `*` , desto större sannolikhet desto större är stapeln.</span><span class="sxs-lookup"><span data-stu-id="c4788-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="c4788-185">För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:</span><span class="sxs-lookup"><span data-stu-id="c4788-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="c4788-186">Följande exempel visar `DumpMachine` för några vanliga tillstånd:</span><span class="sxs-lookup"><span data-stu-id="c4788-186">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="c4788-187">ID: t för en qubit tilldelas vid körning och är inte nödvändigt vis justerat i den ordning som qubit har allokerats eller dess position i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="c4788-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c4788-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c4788-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="c4788-189">Du kan hitta ett qubit-ID i Visual Studio genom att placera en Bryt punkt i koden och inspektera värdet för en qubit-variabel, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c4788-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visa qubit-ID i Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="c4788-191">qubit med index `0` on `register2` har ID = `3` , qubit med index `1` har ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="c4788-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c4788-192">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4788-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="c4788-193">Du kan hitta ett qubit-ID med hjälp av <xref:microsoft.quantum.intrinsic.message> funktionen och skicka qubit-variabeln i meddelandet, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c4788-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="c4788-194">vilket kan generera följande utdata:</span><span class="sxs-lookup"><span data-stu-id="c4788-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="c4788-195">vilket innebär att qubit med index `0` on `register2` har ID = `3` , qubit med index `1` har ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="c4788-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="c4788-196">Eftersom <xref:microsoft.quantum.diagnostics.dumpmachine> är en del av <xref:microsoft.quantum.diagnostics> namn området måste du lägga till en `open` instruktion för att få åtkomst till den:</span><span class="sxs-lookup"><span data-stu-id="c4788-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="c4788-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="c4788-197">DumpRegister</span></span>

<span data-ttu-id="c4788-198"><xref:microsoft.quantum.diagnostics.dumpregister>fungerar som <xref:microsoft.quantum.diagnostics.dumpmachine> , förutom att det också tar en matris med qubits för att begränsa den mängd information som är relevant för motsvarande qubits.</span><span class="sxs-lookup"><span data-stu-id="c4788-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="c4788-199">Precis som med är <xref:microsoft.quantum.diagnostics.dumpmachine> den information som genereras av <xref:microsoft.quantum.diagnostics.dumpregister> beroende av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="c4788-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="c4788-200">För den fulla tillstånds Quantum simulatorn skriver den till filen Wave-funktionen till en global fas av det Quantum-underordnade systemet som genererats av den angivna qubits i samma format som <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="c4788-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="c4788-201">Till exempel ta en gång till en dator med endast två qubits tilldelade och i Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ anrop <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[0]` genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="c4788-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c4788-202">och anrop <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[1]` genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="c4788-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="c4788-203">I allmänhet är statusen för ett register som är Entangled med ett annat register blandat, i stället för ett rent tillstånd.</span><span class="sxs-lookup"><span data-stu-id="c4788-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="c4788-204">I det här fallet ger <xref:microsoft.quantum.diagnostics.dumpregister> följande meddelande utdata:</span><span class="sxs-lookup"><span data-stu-id="c4788-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="c4788-205">I följande exempel visas hur du kan använda både <xref:microsoft.quantum.diagnostics.dumpregister> och <xref:microsoft.quantum.diagnostics.dumpmachine> i din Q# kod:</span><span class="sxs-lookup"><span data-stu-id="c4788-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="c4788-206">Felsökning</span><span class="sxs-lookup"><span data-stu-id="c4788-206">Debugging</span></span>

<span data-ttu-id="c4788-207">Utöver funktionerna och `Assert` `Dump` fungerar har stöd för Q# en delmängd av standard funktioner för Visual Studio-fel sökning: [ställa in rad Bryt punkter](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stega igenom kod med hjälp av F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)och [kontrol lera att värden för klassiska variabler](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) är möjliga vid kod körning i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="c4788-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="c4788-208">Fel sökning i Visual Studio Code utnyttjar de fel söknings funktioner som anges i C# för Visual Studio Code-tillägg som drivs av OmniSharp och som kräver installation av den [senaste versionen](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="c4788-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
