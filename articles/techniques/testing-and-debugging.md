---
title: 'Q #-tekniker – testning och fel sökning | Microsoft Docs'
description: 'Q #-tekniker – testning och fel sökning'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183496"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="116e8-103">Testning och fel sökning</span><span class="sxs-lookup"><span data-stu-id="116e8-103">Testing and Debugging</span></span>

<span data-ttu-id="116e8-104">Precis som med klassisk programmering är det viktigt att kunna kontrol lera att Quantum-programmen fungerar som avsett och att kunna diagnostisera ett Quantum-program som är felaktigt.</span><span class="sxs-lookup"><span data-stu-id="116e8-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="116e8-105">I det här avsnittet tar vi upp de verktyg som erbjuds av Q # för testning och fel sökning av Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="116e8-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="116e8-106">Enhets tester</span><span class="sxs-lookup"><span data-stu-id="116e8-106">Unit Tests</span></span>

<span data-ttu-id="116e8-107">En vanlig metod för att testa klassiska program är att skriva små program som heter *enhets test* som kör kod i ett bibliotek och jämför dess utdata med förväntade utdata.</span><span class="sxs-lookup"><span data-stu-id="116e8-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="116e8-108">Vi kanske till exempel vill se till att `Square(2)` returnerar `4`, eftersom vi vet *en tidigare* version av $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="116e8-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="116e8-109">Q # stöder skapande av enhets test för Quantum-program och som kan köras som tester i [xUnit](https://xunit.github.io/) unit test Framework.</span><span class="sxs-lookup"><span data-stu-id="116e8-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="116e8-110">Skapa ett test projekt</span><span class="sxs-lookup"><span data-stu-id="116e8-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="116e8-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="116e8-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="116e8-112">Öppna Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="116e8-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="116e8-113">Gå till `File`-menyn och välj `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="116e8-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="116e8-114">Välj `Q# Test Project` mall under `Installed` > `Visual C#`i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="116e8-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="116e8-115">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116e8-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="116e8-116">Kör följande kommando från din favorit kommando rad:</span><span class="sxs-lookup"><span data-stu-id="116e8-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="116e8-117">I båda fallen kommer det nya projektet att ha två öppna filer.</span><span class="sxs-lookup"><span data-stu-id="116e8-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="116e8-118">Den första filen `Tests.qs`, är en lämplig plats för att definiera nya Q # Unit-tester.</span><span class="sxs-lookup"><span data-stu-id="116e8-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="116e8-119">Inlednings vis innehåller den här filen en test `AllocateQubitTest` som kontrollerar att en nyligen allokerad qubit är i läget $ \ket{0}$ och skriver ut ett meddelande:</span><span class="sxs-lookup"><span data-stu-id="116e8-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="116e8-120">Alla Q #-åtgärder som är kompatibla med typen `(Unit => Unit)` eller funktionen som är kompatibla med `(Unit -> Unit)` kan köras som ett enhets test.</span><span class="sxs-lookup"><span data-stu-id="116e8-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="116e8-121">Den andra filen `TestSuiteRunner.cs` innehåller en metod som används för att identifiera och köra Q # Unit-tester.</span><span class="sxs-lookup"><span data-stu-id="116e8-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="116e8-122">Detta är metoden `TestTarget` som är kommenterad med `OperationDriver` attribut.</span><span class="sxs-lookup"><span data-stu-id="116e8-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="116e8-123">`OperationDriver`-attributet ingår i Xunit-tilläggs biblioteket Microsoft. Quantum. simulering. Xunit.</span><span class="sxs-lookup"><span data-stu-id="116e8-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="116e8-124">Enhets test ramverket anropar `TestTarget` metod för varje Q # enhets test som har identifierats.</span><span class="sxs-lookup"><span data-stu-id="116e8-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="116e8-125">Ramverket skickar beskrivningen av enhets test till metoden via `op` argument.</span><span class="sxs-lookup"><span data-stu-id="116e8-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="116e8-126">Följande kodrad:</span><span class="sxs-lookup"><span data-stu-id="116e8-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="116e8-127">Kör enhets testet på `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="116e8-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="116e8-128">Som standard söker mekanismen för enhets test identifiering efter alla Q #-funktioner eller-åtgärder av kompatibel typ som uppfyller följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="116e8-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="116e8-129">Placeras i samma sammansättning som metoden som är kommenterad med `OperationDriver`-attributet.</span><span class="sxs-lookup"><span data-stu-id="116e8-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="116e8-130">Finns i samma namnrymd som metoden som är kommenterad med `OperationDriver`-attributet.</span><span class="sxs-lookup"><span data-stu-id="116e8-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="116e8-131">Har ett namn som slutar med `Test`.</span><span class="sxs-lookup"><span data-stu-id="116e8-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="116e8-132">En sammansättning, ett namn område och ett suffix för enhets test funktioner och åtgärder kan anges med valfria parametrar för attributet `OperationDriver`:</span><span class="sxs-lookup"><span data-stu-id="116e8-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="116e8-133">`AssemblyName` parameter anger namnet på sammansättningen som genomsöks efter tester.</span><span class="sxs-lookup"><span data-stu-id="116e8-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="116e8-134">`TestNamespace` parameter anger namnet på namn området som söks efter tester.</span><span class="sxs-lookup"><span data-stu-id="116e8-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="116e8-135">`Suffix` anger suffixet för åtgärds-eller funktions namn som anses vara enhets test.</span><span class="sxs-lookup"><span data-stu-id="116e8-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="116e8-136">Dessutom kan du med `TestCasePrefix` valfria parametern ange ett prefix för namnet på test ärendet.</span><span class="sxs-lookup"><span data-stu-id="116e8-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="116e8-137">Prefixet framför åtgärds namnet visas i listan över test fall.</span><span class="sxs-lookup"><span data-stu-id="116e8-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="116e8-138">`TestCasePrefix = "QSim:"` kan till exempel göra att `AllocateQubitTest` visas som `QSim:AllocateQubitTest` i listan med hittade tester.</span><span class="sxs-lookup"><span data-stu-id="116e8-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="116e8-139">Detta kan vara användbart för att indikera till exempel vilken simulator som används för att köra ett test.</span><span class="sxs-lookup"><span data-stu-id="116e8-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="116e8-140">Köra Q # enhets test</span><span class="sxs-lookup"><span data-stu-id="116e8-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="116e8-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="116e8-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="116e8-142">Som en konfiguration per lösning går du till `Test`-menyn och väljer `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="116e8-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="116e8-143">Standardinställningen för processor arkitektur för Visual Studio lagras i lösnings alternativ filen (`.suo`) för varje lösning.</span><span class="sxs-lookup"><span data-stu-id="116e8-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="116e8-144">Om du tar bort den här filen måste du välja `X64` som processor arkitektur igen.</span><span class="sxs-lookup"><span data-stu-id="116e8-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="116e8-145">Bygg projektet, gå till `Test`-menyn och välj `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="116e8-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="116e8-146">`AllocateQubitTest` visas i listan med tester i `Not Run Tests`s gruppen.</span><span class="sxs-lookup"><span data-stu-id="116e8-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="116e8-147">Välj `Run All` eller kör det här enskilda testet så bör det passas!</span><span class="sxs-lookup"><span data-stu-id="116e8-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="116e8-148">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116e8-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="116e8-149">Om du vill köra tester navigerar du till projektmappen (mappen som innehåller `Tests.csproj`) och kör kommandot:</span><span class="sxs-lookup"><span data-stu-id="116e8-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="116e8-150">Du bör få utdata som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="116e8-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="116e8-151">Loggning och intyg</span><span class="sxs-lookup"><span data-stu-id="116e8-151">Logging and Assertions</span></span>

<span data-ttu-id="116e8-152">En viktig följd av det faktum att funktioner i Q # inte har några sido effekter är att alla effekter av att köra en funktion vars Utdatatyp är den tomma tuppeln `()` aldrig kan observeras i ett Q #-program.</span><span class="sxs-lookup"><span data-stu-id="116e8-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="116e8-153">Det innebär att en måldator kan välja att inte köra någon funktion som returnerar `()` med garantin att detta utelämnande inte ändrar beteendet för någon av följande Q #-koder.</span><span class="sxs-lookup"><span data-stu-id="116e8-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="116e8-154">Detta gör att funktioner returnerar `()` ett användbart verktyg för att bädda in kontroller och fel söknings logik i Q #-program.</span><span class="sxs-lookup"><span data-stu-id="116e8-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="116e8-155">Loggning</span><span class="sxs-lookup"><span data-stu-id="116e8-155">Logging</span></span>

<span data-ttu-id="116e8-156">Den inbyggda funktionen <xref:microsoft.quantum.intrinsic.message> har typen `(String -> Unit)` och gör det möjligt att skapa diagnostiska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="116e8-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="116e8-157">`onLog` åtgärden för `QuantumSimulator` kan användas för att definiera åtgärder som utförs när Q # Code-anrop `Message`.</span><span class="sxs-lookup"><span data-stu-id="116e8-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="116e8-158">Som standard skrivs loggade meddelanden ut till standardutdata.</span><span class="sxs-lookup"><span data-stu-id="116e8-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="116e8-159">När du definierar en enhets tests Suite kan de loggade meddelandena dirigeras till test resultatet.</span><span class="sxs-lookup"><span data-stu-id="116e8-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="116e8-160">När ett projekt skapas från en test projekt mal len för Q #, är denna omdirigering förkonfigurerad för sviten och skapas som standard enligt följande:</span><span class="sxs-lookup"><span data-stu-id="116e8-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="116e8-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="116e8-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="116e8-162">När du har kört ett test i test Utforskaren och klickar på testet visas en panel med information om testkörning: status för skickad/misslyckad, förfluten tid och en "utdata"-länk.</span><span class="sxs-lookup"><span data-stu-id="116e8-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="116e8-163">Om du klickar på länken "utdata" öppnas test resultatet i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="116e8-163">If you click the "Output" link, test output will open in a new window.</span></span>

![testa utdata](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="116e8-165">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116e8-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="116e8-166">Status för pass/misslyckande för varje test skrivs ut till-konsolen med `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="116e8-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="116e8-167">Vid misslyckade tester skrivs utdata som loggats till följd av `output.WriteLine(msg)` anropet ovan också till-konsolen för att hjälpa till att diagnostisera felet.</span><span class="sxs-lookup"><span data-stu-id="116e8-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="116e8-168">Intyg</span><span class="sxs-lookup"><span data-stu-id="116e8-168">Assertions</span></span>

<span data-ttu-id="116e8-169">Samma logik kan användas för att implementera kontroller.</span><span class="sxs-lookup"><span data-stu-id="116e8-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="116e8-170">Vi ska tänka på ett enkelt exempel:</span><span class="sxs-lookup"><span data-stu-id="116e8-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="116e8-171">Här anger nyckelordet `fail` att beräkningen inte bör fortsätta, vilket ger upphov till ett undantag på mål datorn som kör Q #-programmet.</span><span class="sxs-lookup"><span data-stu-id="116e8-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="116e8-172">Efter definition kan ett problem av den här typen inte observeras inifrån Q # eftersom ingen ytterligare Q # kod körs när en `fail`-instruktion har nåtts.</span><span class="sxs-lookup"><span data-stu-id="116e8-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="116e8-173">Om vi fortsätter att passera ett anrop till `AssertPositive`, kan vi därför vara säkra på att dess inaktuella information var positiv.</span><span class="sxs-lookup"><span data-stu-id="116e8-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="116e8-174">[Inledning](xref:microsoft.quantum.libraries.standard.prelude) erbjuder två särskilt användbara kontroller, <xref:microsoft.quantum.intrinsic.assert> och <xref:microsoft.quantum.intrinsic.assertprob> både modellerade som åtgärder på `()`.</span><span class="sxs-lookup"><span data-stu-id="116e8-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="116e8-175">Dessa intyg var och en tar en Pauli-operatör som beskriver en viss värdering av intresse, ett Quantum-register som en mätning ska utföras på och ett hypotetiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="116e8-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="116e8-176">På mål datorer som arbetar med simuleringen är vi inte kopplade till [no-kloning-satsen](https://en.wikipedia.org/wiki/No-cloning_theorem)och kan utföra sådana mätningar utan att störa registret som skickats till sådana kontroller.</span><span class="sxs-lookup"><span data-stu-id="116e8-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="116e8-177">En simulator kan sedan, som liknar `AssertPositive` funktion ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i övningen:</span><span class="sxs-lookup"><span data-stu-id="116e8-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="116e8-178">På fysisk Quantum-maskinvara där ingen-kloning-satsen förhindrar granskning av Quantum-tillstånd, returnerar `Assert` och `AssertProb` åtgärder bara `()` utan någon annan påverkan.</span><span class="sxs-lookup"><span data-stu-id="116e8-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="116e8-179"><xref:microsoft.quantum.diagnostics>-namnrymden innehåller flera fler funktioner i `Assert`-serien som gör det möjligt för oss att kontrol lera mer avancerade villkor.</span><span class="sxs-lookup"><span data-stu-id="116e8-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="116e8-180">Dumpa funktioner</span><span class="sxs-lookup"><span data-stu-id="116e8-180">Dump Functions</span></span>

<span data-ttu-id="116e8-181">För att hjälpa till att felsöka Quantum-program erbjuder <xref:microsoft.quantum.diagnostics>-namnrymden två funktioner som kan dumpa till en fil aktuella status för mål datorn: <xref:microsoft.quantum.diagnostics.dumpmachine> och <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="116e8-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="116e8-182">De utdata som genereras av var och en beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="116e8-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="116e8-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="116e8-183">DumpMachine</span></span>

<span data-ttu-id="116e8-184">Den fullständiga Quantum-simulatorn som distribueras som en del av Quantum Development Kit skriver till filen [Wave-funktionen](https://en.wikipedia.org/wiki/Wave_function) i hela Quantum-systemet, som en endimensionell matris med komplexa tal, där varje element representerar amplituden för sannolikhet för mätning av beräknings bas tillstånd $ \ket{n} $, där $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ för BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="116e8-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="116e8-185">Till exempel på en dator som bara har två qubits allokerade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpmachine> genererar dessa utdata :</span><span class="sxs-lookup"><span data-stu-id="116e8-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="116e8-186">Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.</span><span class="sxs-lookup"><span data-stu-id="116e8-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="116e8-187">Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{n} $ i båda formaten kartesiska och Polar.</span><span class="sxs-lookup"><span data-stu-id="116e8-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="116e8-188">I detalj för den första raden:</span><span class="sxs-lookup"><span data-stu-id="116e8-188">In detail for the first row:</span></span>

* <span data-ttu-id="116e8-189">**`∣0❭:`** den här raden motsvarar `0` beräknings bas status</span><span class="sxs-lookup"><span data-stu-id="116e8-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="116e8-190">**`0.707107 +  0.000000 i`** : sannolikheten amplitud i kartesiska-format.</span><span class="sxs-lookup"><span data-stu-id="116e8-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="116e8-191">**` == `** : `equal`-tecknet separerar både motsvarande representationer.</span><span class="sxs-lookup"><span data-stu-id="116e8-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="116e8-192">**`**********  `** : en grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta denna tillstånds vektor.</span><span class="sxs-lookup"><span data-stu-id="116e8-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="116e8-193">**`[ 0.500000 ]`** : det numeriska värdet för förstornas storlek</span><span class="sxs-lookup"><span data-stu-id="116e8-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="116e8-194">**`    ---`** : en grafisk representation av amplitudens fas (se nedan).</span><span class="sxs-lookup"><span data-stu-id="116e8-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="116e8-195">**`[ 0.0000 rad ]`** : det numeriska värdet för fasen (i radianer).</span><span class="sxs-lookup"><span data-stu-id="116e8-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="116e8-196">Både storleken och fasen visas med en grafisk representation.</span><span class="sxs-lookup"><span data-stu-id="116e8-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="116e8-197">Representation av storlek är rak: det visar ett stapeldiagram med `*`desto större sannolikhet desto större stapel blir.</span><span class="sxs-lookup"><span data-stu-id="116e8-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="116e8-198">För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:</span><span class="sxs-lookup"><span data-stu-id="116e8-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="116e8-199">I följande exempel visas `DumpMachine` för några vanliga tillstånd:</span><span class="sxs-lookup"><span data-stu-id="116e8-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="116e8-200">ID: t för en qubit tilldelas vid körning och är inte nödvändigt vis justerat i den ordning som qubit allokerades eller var i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="116e8-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="116e8-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="116e8-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="116e8-202">Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en Bryt punkt i koden och inspektera värdet för en qubit-variabel, till exempel:</span><span class="sxs-lookup"><span data-stu-id="116e8-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visa qubit-ID i Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="116e8-204">qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="116e8-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="116e8-205">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116e8-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="116e8-206">Du kan räkna ut ett qubit-ID med hjälp av funktionen <xref:microsoft.quantum.intrinsic.message> och skicka qubit-variabeln i meddelandet, till exempel:</span><span class="sxs-lookup"><span data-stu-id="116e8-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="116e8-207">vilket kan generera följande utdata:</span><span class="sxs-lookup"><span data-stu-id="116e8-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="116e8-208">vilket innebär att qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="116e8-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="116e8-209"><xref:microsoft.quantum.diagnostics.dumpmachine> är en del av <xref:microsoft.quantum.diagnostics>-namnområdet så att du måste lägga till ett `open`-uttryck för att kunna använda det:</span><span class="sxs-lookup"><span data-stu-id="116e8-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="116e8-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="116e8-210">DumpRegister</span></span>

<span data-ttu-id="116e8-211"><xref:microsoft.quantum.diagnostics.dumpregister> fungerar som <xref:microsoft.quantum.diagnostics.dumpmachine>, förutom att det också tar en matris med qubits för att begränsa den mängd information som är relevant för motsvarande qubits.</span><span class="sxs-lookup"><span data-stu-id="116e8-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="116e8-212">Precis som med <xref:microsoft.quantum.diagnostics.dumpmachine>är den information som genereras av <xref:microsoft.quantum.diagnostics.dumpregister> beroende av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="116e8-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="116e8-213">För den fulla tillstånds Quantum simulatorn skrivs den till filen Wave-funktionen till en global fas av det Quantum-underordnade systemet som genererats av den angivna qubits i samma format som <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="116e8-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="116e8-214">Ta till exempel en dator med endast två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ anropa <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[0]` genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="116e8-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="116e8-215">och anropar <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[1]` genererar följande utdata:</span><span class="sxs-lookup"><span data-stu-id="116e8-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="116e8-216">I allmänhet är statusen för ett register som är Entangled med ett annat register blandat, i stället för ett rent tillstånd.</span><span class="sxs-lookup"><span data-stu-id="116e8-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="116e8-217">I det här fallet <xref:microsoft.quantum.diagnostics.dumpregister> utdata i följande meddelande:</span><span class="sxs-lookup"><span data-stu-id="116e8-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="116e8-218">I följande exempel visas hur du kan använda både <xref:microsoft.quantum.diagnostics.dumpregister> och <xref:microsoft.quantum.diagnostics.dumpmachine> i din Q #-kod:</span><span class="sxs-lookup"><span data-stu-id="116e8-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="116e8-219">Felsökning</span><span class="sxs-lookup"><span data-stu-id="116e8-219">Debugging</span></span>

<span data-ttu-id="116e8-220">Utöver `Assert` och `Dump` funktioner och åtgärder stöder Q # en delmängd av standard funktioner för Visual Studio-fel sökning: [Ange rad Bryt punkter](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stega genom kod med hjälp av F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [inspektera värden för klassiska variabler ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)är allt möjligt vid kod körning i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="116e8-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="116e8-221">Det finns ännu inte stöd för fel sökning i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="116e8-221">Debugging in Visual Studio Code is not yet supported.</span></span>

