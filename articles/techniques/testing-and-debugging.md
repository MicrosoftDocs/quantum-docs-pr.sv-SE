---
title: 'Q #-tekniker – testning och fel sökning | Microsoft Docs'
description: 'Q #-tekniker – testning och fel sökning'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d352ffa315b654cfcf8991fa116465d3dad49f0a
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864278"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="2b260-103">Testning och fel sökning</span><span class="sxs-lookup"><span data-stu-id="2b260-103">Testing and Debugging</span></span>

<span data-ttu-id="2b260-104">Precis som med klassisk programmering är det viktigt att kunna kontrol lera att Quantum-programmen fungerar som avsett och att kunna diagnostisera ett Quantum-program som är felaktigt.</span><span class="sxs-lookup"><span data-stu-id="2b260-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="2b260-105">I det här avsnittet tar vi upp de verktyg som erbjuds av Q # för testning och fel sökning av Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="2b260-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="2b260-106">Enhets tester</span><span class="sxs-lookup"><span data-stu-id="2b260-106">Unit Tests</span></span>

<span data-ttu-id="2b260-107">En vanlig metod för att testa klassiska program är att skriva små program som heter *enhets test* som kör kod i ett bibliotek och jämför dess utdata med förväntade utdata.</span><span class="sxs-lookup"><span data-stu-id="2b260-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="2b260-108">Vi kanske till exempel vill se till att `Square(2)` returnerar `4`, eftersom vi vet *en tidigare* version av $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="2b260-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="2b260-109">Q # stöder skapande av enhets test för Quantum-program och som kan köras som tester i [xUnit](https://xunit.github.io/) unit test Framework.</span><span class="sxs-lookup"><span data-stu-id="2b260-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="2b260-110">Skapa ett test projekt</span><span class="sxs-lookup"><span data-stu-id="2b260-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b260-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b260-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b260-112">Öppna Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="2b260-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="2b260-113">Gå till `File`-menyn och välj `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="2b260-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="2b260-114">I det övre högra hörnet söker du efter `Q#`och väljer `Q# Test Project`s mal len.</span><span class="sxs-lookup"><span data-stu-id="2b260-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b260-115">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b260-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b260-116">Kör följande kommando från din favorit kommando rad:</span><span class="sxs-lookup"><span data-stu-id="2b260-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="2b260-117">Det nya projektet kommer att ha en enda fil `Tests.qs`, vilket ger en bra plats för att definiera nya Q # Unit-tester.</span><span class="sxs-lookup"><span data-stu-id="2b260-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="2b260-118">Inlednings vis innehåller den här filen en test `AllocateQubit` som kontrollerar att en nyligen allokerad qubit är i läget $ \ket{0}$ och skriver ut ett meddelande:</span><span class="sxs-lookup"><span data-stu-id="2b260-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="2b260-119">: ny: varje Q #-åtgärd eller funktion som tar ett argument av typen `Unit` och returnerar `Unit` kan markeras som ett enhets test via `@Test("...")`-attributet.</span><span class="sxs-lookup"><span data-stu-id="2b260-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="2b260-120">Argumentet till detta attribut, `"QuantumSimulator"` ovan, anger målet som testet körs på.</span><span class="sxs-lookup"><span data-stu-id="2b260-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="2b260-121">Ett enda test kan köras på flera mål.</span><span class="sxs-lookup"><span data-stu-id="2b260-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="2b260-122">Lägg till exempel till ett attribut `@Test("ResourcesEstimator")` ovan `AllocateQubit`.</span><span class="sxs-lookup"><span data-stu-id="2b260-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="2b260-123">Spara filen och kör alla tester.</span><span class="sxs-lookup"><span data-stu-id="2b260-123">Save the file and execute all tests.</span></span> <span data-ttu-id="2b260-124">Det bör nu finnas två enhets test, en där AllocateQubit körs på QuantumSimulator och en där den körs i ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="2b260-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="2b260-125">I Q #-kompilatorn identifieras de inbyggda målen "QuantumSimulator", "ToffoliSimulator" och "ResourcesEstimator" som giltiga körnings mål för enhets tester.</span><span class="sxs-lookup"><span data-stu-id="2b260-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="2b260-126">Det är också möjligt att ange ett fullständigt kvalificerat namn för att definiera ett anpassat körnings mål.</span><span class="sxs-lookup"><span data-stu-id="2b260-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="2b260-127">Köra Q # enhets test</span><span class="sxs-lookup"><span data-stu-id="2b260-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b260-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b260-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b260-129">Som en konfiguration per lösning går du till `Test`-menyn och väljer `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="2b260-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="2b260-130">Standardinställningen för processor arkitektur för Visual Studio lagras i lösnings alternativ filen (`.suo`) för varje lösning.</span><span class="sxs-lookup"><span data-stu-id="2b260-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="2b260-131">Om du tar bort den här filen måste du välja `X64` som processor arkitektur igen.</span><span class="sxs-lookup"><span data-stu-id="2b260-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="2b260-132">Bygg projektet, gå till `Test`-menyn och välj `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="2b260-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="2b260-133">`AllocateQubit` visas i listan med tester i `Not Run Tests`s gruppen.</span><span class="sxs-lookup"><span data-stu-id="2b260-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="2b260-134">Välj `Run All` eller kör det här enskilda testet så bör det passas!</span><span class="sxs-lookup"><span data-stu-id="2b260-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b260-135">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b260-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b260-136">Om du vill köra tester navigerar du till projektmappen (mappen som innehåller `Tests.csproj`) och kör kommandot:</span><span class="sxs-lookup"><span data-stu-id="2b260-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="2b260-137">Du bör få utdata som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="2b260-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="2b260-138">Enhets test kan filtreras efter namn och/eller körnings mål:</span><span class="sxs-lookup"><span data-stu-id="2b260-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="2b260-139">Den inbyggda funktionen <xref:microsoft.quantum.intrinsic.message> har typen `(String -> Unit)` och gör det möjligt att skapa diagnostiska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2b260-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b260-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b260-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b260-141">När du har kört ett test i test Utforskaren och klickar på testet visas en panel med information om testkörning: status för skickad/misslyckad, förfluten tid och en "utdata"-länk.</span><span class="sxs-lookup"><span data-stu-id="2b260-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="2b260-142">Om du klickar på länken "utdata" öppnas test resultatet i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="2b260-142">If you click the "Output" link, test output will open in a new window.</span></span>

![testa utdata](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b260-144">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b260-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b260-145">Status för pass/misslyckande för varje test skrivs ut till-konsolen med `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2b260-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="2b260-146">Vid misslyckade tester skrivs utdata också ut till-konsolen för att hjälpa till att diagnostisera felet.</span><span class="sxs-lookup"><span data-stu-id="2b260-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="assertions"></a><span data-ttu-id="2b260-147">Intyg</span><span class="sxs-lookup"><span data-stu-id="2b260-147">Assertions</span></span>

<span data-ttu-id="2b260-148">Eftersom funktioner i Q # inte har några _logiska_ sid effekter, kan alla _andra typer_ av effekter av att köra en funktion vars datatyp är den tomma tuppeln `()` aldrig observeras i ett Q #-program.</span><span class="sxs-lookup"><span data-stu-id="2b260-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="2b260-149">Det innebär att en måldator kan välja att inte köra någon funktion som returnerar `()` med garantin att detta utelämnande inte ändrar beteendet för någon av följande Q #-koder.</span><span class="sxs-lookup"><span data-stu-id="2b260-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="2b260-150">Detta gör att funktioner returnerar `()` ett användbart verktyg för att bädda in kontroller och fel söknings logik i Q #-program.</span><span class="sxs-lookup"><span data-stu-id="2b260-150">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="2b260-151">Samma logik kan användas för att implementera kontroller.</span><span class="sxs-lookup"><span data-stu-id="2b260-151">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="2b260-152">Vi ska tänka på ett enkelt exempel:</span><span class="sxs-lookup"><span data-stu-id="2b260-152">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="2b260-153">Här anger nyckelordet `fail` att beräkningen inte bör fortsätta, vilket ger upphov till ett undantag på mål datorn som kör Q #-programmet.</span><span class="sxs-lookup"><span data-stu-id="2b260-153">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="2b260-154">Efter definition kan ett problem av den här typen inte observeras inifrån Q # eftersom ingen ytterligare Q # kod körs när en `fail`-instruktion har nåtts.</span><span class="sxs-lookup"><span data-stu-id="2b260-154">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="2b260-155">Om vi fortsätter att passera ett anrop till `AssertPositive`, kan vi därför vara säkra på att dess inaktuella information var positiv.</span><span class="sxs-lookup"><span data-stu-id="2b260-155">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="2b260-156">[Inledning](xref:microsoft.quantum.libraries.standard.prelude) erbjuder två särskilt användbara kontroller, <xref:microsoft.quantum.intrinsic.assert> och <xref:microsoft.quantum.intrinsic.assertprob> både modellerade som åtgärder på `()`.</span><span class="sxs-lookup"><span data-stu-id="2b260-156">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="2b260-157">Dessa intyg var och en tar en Pauli-operatör som beskriver en viss värdering av intresse, ett Quantum-register som en mätning ska utföras på och ett hypotetiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="2b260-157">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="2b260-158">På mål datorer som arbetar med simuleringen är vi inte kopplade till [no-kloning-satsen](https://en.wikipedia.org/wiki/No-cloning_theorem)och kan utföra sådana mätningar utan att störa registret som skickats till sådana kontroller.</span><span class="sxs-lookup"><span data-stu-id="2b260-158">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="2b260-159">En simulator kan sedan, som liknar `AssertPositive` funktion ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i övningen:</span><span class="sxs-lookup"><span data-stu-id="2b260-159">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="2b260-160">På fysisk Quantum-maskinvara där ingen-kloning-satsen förhindrar granskning av Quantum-tillstånd, returnerar `Assert` och `AssertProb` åtgärder bara `()` utan någon annan påverkan.</span><span class="sxs-lookup"><span data-stu-id="2b260-160">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="2b260-161"><xref:microsoft.quantum.diagnostics>-namnrymden innehåller flera fler funktioner i `Assert`-serien som gör det möjligt för oss att kontrol lera mer avancerade villkor.</span><span class="sxs-lookup"><span data-stu-id="2b260-161">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="2b260-162">Dumpa funktioner</span><span class="sxs-lookup"><span data-stu-id="2b260-162">Dump Functions</span></span>

<span data-ttu-id="2b260-163">För att hjälpa till att felsöka Quantum-program erbjuder <xref:microsoft.quantum.diagnostics>-namnrymden två funktioner som kan dumpa till en fil aktuella status för mål datorn: <xref:microsoft.quantum.diagnostics.dumpmachine> och <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="2b260-163">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="2b260-164">De utdata som genereras av var och en beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="2b260-164">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="2b260-165">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="2b260-165">DumpMachine</span></span>

<span data-ttu-id="2b260-166">Den fullständiga Quantum-simulatorn som distribueras som en del av Quantum Development Kit skriver till filen [Wave-funktionen](https://en.wikipedia.org/wiki/Wave_function) i hela Quantum-systemet, som en endimensionell matris med komplexa tal, där varje element representerar amplituden av sannolikheten för att mäta beräknings bas status $ \ket{n} $, där $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ för BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="2b260-166">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="2b260-167">Till exempel på en dator som bara har två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ anropa <xref:microsoft.quantum.diagnostics.dumpmachine> genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="2b260-167">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="2b260-168">Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.</span><span class="sxs-lookup"><span data-stu-id="2b260-168">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="2b260-169">Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{n} $ i båda formaten kartesiska och Polar.</span><span class="sxs-lookup"><span data-stu-id="2b260-169">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="2b260-170">I detalj för den första raden:</span><span class="sxs-lookup"><span data-stu-id="2b260-170">In detail for the first row:</span></span>

* <span data-ttu-id="2b260-171">**`∣0❭:`** den här raden motsvarar `0` beräknings bas status</span><span class="sxs-lookup"><span data-stu-id="2b260-171">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="2b260-172">**`0.707107 +  0.000000 i`** : sannolikheten amplitud i kartesiska-format.</span><span class="sxs-lookup"><span data-stu-id="2b260-172">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="2b260-173">**` == `** : `equal`-tecknet separerar både motsvarande representationer.</span><span class="sxs-lookup"><span data-stu-id="2b260-173">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="2b260-174">**`**********  `** : en grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta denna tillstånds vektor.</span><span class="sxs-lookup"><span data-stu-id="2b260-174">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="2b260-175">**`[ 0.500000 ]`** : det numeriska värdet för förstornas storlek</span><span class="sxs-lookup"><span data-stu-id="2b260-175">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="2b260-176">**`    ---`** : en grafisk representation av amplitudens fas (se nedan).</span><span class="sxs-lookup"><span data-stu-id="2b260-176">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="2b260-177">**`[ 0.0000 rad ]`** : det numeriska värdet för fasen (i radianer).</span><span class="sxs-lookup"><span data-stu-id="2b260-177">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="2b260-178">Både storleken och fasen visas med en grafisk representation.</span><span class="sxs-lookup"><span data-stu-id="2b260-178">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="2b260-179">Representation av storlek är rak: det visar ett stapeldiagram med `*`desto större sannolikhet desto större stapel blir.</span><span class="sxs-lookup"><span data-stu-id="2b260-179">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="2b260-180">För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:</span><span class="sxs-lookup"><span data-stu-id="2b260-180">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="2b260-181">I följande exempel visas `DumpMachine` för några vanliga tillstånd:</span><span class="sxs-lookup"><span data-stu-id="2b260-181">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="2b260-182">ID: t för en qubit tilldelas vid körning och är inte nödvändigt vis justerat i den ordning som qubit allokerades eller var i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="2b260-182">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b260-183">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b260-183">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="2b260-184">Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en Bryt punkt i koden och inspektera värdet för en qubit-variabel, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2b260-184">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visa qubit-ID i Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="2b260-186">qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="2b260-186">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b260-187">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b260-187">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="2b260-188">Du kan räkna ut ett qubit-ID med hjälp av funktionen <xref:microsoft.quantum.intrinsic.message> och skicka qubit-variabeln i meddelandet, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2b260-188">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="2b260-189">vilket kan generera följande utdata:</span><span class="sxs-lookup"><span data-stu-id="2b260-189">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="2b260-190">vilket innebär att qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="2b260-190">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="2b260-191"><xref:microsoft.quantum.diagnostics.dumpmachine> är en del av <xref:microsoft.quantum.diagnostics>-namnområdet så att du måste lägga till ett `open`-uttryck för att kunna använda det:</span><span class="sxs-lookup"><span data-stu-id="2b260-191"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="2b260-192">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="2b260-192">DumpRegister</span></span>

<span data-ttu-id="2b260-193"><xref:microsoft.quantum.diagnostics.dumpregister> fungerar som <xref:microsoft.quantum.diagnostics.dumpmachine>, förutom att det också tar en matris med qubits för att begränsa den mängd information som är relevant för motsvarande qubits.</span><span class="sxs-lookup"><span data-stu-id="2b260-193"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="2b260-194">Precis som med <xref:microsoft.quantum.diagnostics.dumpmachine>är den information som genereras av <xref:microsoft.quantum.diagnostics.dumpregister> beroende av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="2b260-194">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="2b260-195">För den fulla tillstånds Quantum simulatorn skrivs den till filen Wave-funktionen till en global fas av det Quantum-underordnade systemet som genererats av den angivna qubits i samma format som <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="2b260-195">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="2b260-196">Ta till exempel en dator med endast två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}). \end{align} $ $ som anropar <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[0]` genererar utdata :</span><span class="sxs-lookup"><span data-stu-id="2b260-196">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="2b260-197">och anropar <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[1]` genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="2b260-197">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="2b260-198">I allmänhet är statusen för ett register som är Entangled med ett annat register blandat, i stället för ett rent tillstånd.</span><span class="sxs-lookup"><span data-stu-id="2b260-198">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="2b260-199">I det här fallet <xref:microsoft.quantum.diagnostics.dumpregister> utdata i följande meddelande:</span><span class="sxs-lookup"><span data-stu-id="2b260-199">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="2b260-200">I följande exempel visas hur du kan använda både <xref:microsoft.quantum.diagnostics.dumpregister> och <xref:microsoft.quantum.diagnostics.dumpmachine> i din Q #-kod:</span><span class="sxs-lookup"><span data-stu-id="2b260-200">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="2b260-201">Felsökning</span><span class="sxs-lookup"><span data-stu-id="2b260-201">Debugging</span></span>

<span data-ttu-id="2b260-202">I början av `Assert` och `Dump` funktioner och åtgärder har Q # stöd för en delmängd vanliga fel söknings funktioner i Visual Studio: att [ställa in rad Bryt punkter](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stega igenom kod med hjälp av F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [kontrol lera värden för klassiska variabler](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) är alla möjliga vid kod körning i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="2b260-202">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="2b260-203">Fel sökning i Visual Studio Code utnyttjar de fel söknings funktioner som tillhandahålls av C# för Visual Studio Code-tillägget som drivs av OmniSharp och kräver att den [senaste versionen](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)installeras.</span><span class="sxs-lookup"><span data-stu-id="2b260-203">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
