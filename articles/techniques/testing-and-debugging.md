---
title: Testa och felsöka Q#-program
description: Lär dig hur du använder enhetstester, fakta och påståenden och dumpar funktioner för att testa och felsöka kvantprogram.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030590"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="825ba-103">Testning och felsökning</span><span class="sxs-lookup"><span data-stu-id="825ba-103">Testing and Debugging</span></span>

<span data-ttu-id="825ba-104">Som med klassisk programmering, är det viktigt att kunna kontrollera att kvantprogram fungerar som avsett, och att kunna diagnostisera ett kvantprogram som är felaktigt.</span><span class="sxs-lookup"><span data-stu-id="825ba-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="825ba-105">I det här avsnittet täcker vi de verktyg som erbjuds av Q# för testning och felsökning av kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="825ba-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="825ba-106">Enhetstester</span><span class="sxs-lookup"><span data-stu-id="825ba-106">Unit Tests</span></span>

<span data-ttu-id="825ba-107">En vanlig metod för att testa klassiska program är att skriva små program som kallas *enhetstester* som kör kod i ett bibliotek och jämföra dess produktion till vissa förväntade produktionen.</span><span class="sxs-lookup"><span data-stu-id="825ba-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="825ba-108">Till exempel kanske vi vill `Square(2)` `4`se till att avkastningen , eftersom vi vet *a priori* att $ 2 ^ 2 = 4 $.</span><span class="sxs-lookup"><span data-stu-id="825ba-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="825ba-109">Q# stöder att skapa enhetstester för kvantprogram och som kan utföras som tester inom [testramverket för xUnit-enheten.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="825ba-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="825ba-110">Skapa ett testprojekt</span><span class="sxs-lookup"><span data-stu-id="825ba-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="825ba-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="825ba-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="825ba-112">Öppna Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="825ba-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="825ba-113">Gå till `File` menyn `New`  >  `Project...`och välj .</span><span class="sxs-lookup"><span data-stu-id="825ba-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="825ba-114">Sök efter `Q#`i det övre högra `Q# Test Project` hörnet och välj mallen.</span><span class="sxs-lookup"><span data-stu-id="825ba-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="825ba-115">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="825ba-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="825ba-116">Kör följande kommando på din favoritkommandorad:</span><span class="sxs-lookup"><span data-stu-id="825ba-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="825ba-117">Det nya projektet kommer `Tests.qs`att ha en enda fil, vilket ger en bekväm plats att definiera nya Q# enhetstester.</span><span class="sxs-lookup"><span data-stu-id="825ba-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="825ba-118">Inledningsvis den här filen innehåller `AllocateQubit` ett exempel enhet test som kontrollerar att en{0}nyligen allokerad qubit är i $\ket $ tillstånd och skriver ut ett meddelande:</span><span class="sxs-lookup"><span data-stu-id="825ba-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:ny: <span data-ttu-id="825ba-119">Alla Q#-åtgärder eller -funktioner `Unit` som `Unit` tar ett argument av `@Test("...")` typ och returer kan markeras som ett enhetstest via attributet.</span><span class="sxs-lookup"><span data-stu-id="825ba-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="825ba-120">Argumentet till det `"QuantumSimulator"` attributet anger det mål som testet körs på.</span><span class="sxs-lookup"><span data-stu-id="825ba-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="825ba-121">Ett enda test kan utföras på flera mål.</span><span class="sxs-lookup"><span data-stu-id="825ba-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="825ba-122">Lägg till exempel `@Test("ResourcesEstimator")` till `AllocateQubit`ett attribut ovan .</span><span class="sxs-lookup"><span data-stu-id="825ba-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="825ba-123">Spara filen och kör alla tester.</span><span class="sxs-lookup"><span data-stu-id="825ba-123">Save the file and execute all tests.</span></span> <span data-ttu-id="825ba-124">Det bör nu finnas två enhetstester, en där AllocateQubit körs på QuantumSimulator och en där den körs i ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="825ba-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="825ba-125">Q# kompilatorn känner igen de inbyggda målen "QuantumSimulator", "ToffoliSimulator" och "ResourcesEstimator" som giltiga körningsmål för enhetstester.</span><span class="sxs-lookup"><span data-stu-id="825ba-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="825ba-126">Det är också möjligt att ange alla fullständigt kvalificerade namn för att definiera ett anpassat körningsmål.</span><span class="sxs-lookup"><span data-stu-id="825ba-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="825ba-127">Köra Q# enhetstester</span><span class="sxs-lookup"><span data-stu-id="825ba-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="825ba-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="825ba-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="825ba-129">Som en engångsinställning per lösning går `Test` du `Test Settings`  >  `Default Processor Architecture`  >  `X64`till menyn och väljer .</span><span class="sxs-lookup"><span data-stu-id="825ba-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="825ba-130">Standardinställningen för processorarkitektur för Visual Studio`.suo`lagras i lösningsalternativen ( ) för varje lösning.</span><span class="sxs-lookup"><span data-stu-id="825ba-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="825ba-131">Om du tar bort den här `X64` filen måste du välja som processorarkitektur igen.</span><span class="sxs-lookup"><span data-stu-id="825ba-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="825ba-132">Bygg projektet, gå `Test` till menyn `Windows`  >  `Test Explorer`och välj .</span><span class="sxs-lookup"><span data-stu-id="825ba-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="825ba-133">`AllocateQubit`visas i listan över tester `Not Run Tests` i gruppen.</span><span class="sxs-lookup"><span data-stu-id="825ba-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="825ba-134">Välj `Run All` eller kör detta individuella test, och det bör passera!</span><span class="sxs-lookup"><span data-stu-id="825ba-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="825ba-135">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="825ba-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="825ba-136">Om du vill köra tester navigerar du `Tests.csproj`till projektmappen (mappen som innehåller) och kör kommandot:</span><span class="sxs-lookup"><span data-stu-id="825ba-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="825ba-137">Du bör få utdata som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="825ba-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="825ba-138">Enhetstester kan filtreras efter namn och/eller körningsmål:</span><span class="sxs-lookup"><span data-stu-id="825ba-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="825ba-139">Den inneboende <xref:microsoft.quantum.intrinsic.message> funktionen `(String -> Unit)` har typ och gör det möjligt att skapa diagnostiska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="825ba-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="825ba-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="825ba-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="825ba-141">När du har körat ett test i Test Explorer och klickat på testet visas en panel med information om testkörning: Godkänd/misslyckad status, förfluten tid och en "Utdata"-länk.</span><span class="sxs-lookup"><span data-stu-id="825ba-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="825ba-142">Om du klickar på länken "Utdata" öppnas testutdata i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="825ba-142">If you click the "Output" link, test output will open in a new window.</span></span>

![testutgång](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="825ba-144">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="825ba-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="825ba-145">Statusen godkänd/underkänd för varje test skrivs ut till konsolen av `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="825ba-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="825ba-146">För misslyckade tester skrivs ututgångarna också till konsolen för att diagnostisera felet.</span><span class="sxs-lookup"><span data-stu-id="825ba-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="825ba-147">Fakta och påståenden</span><span class="sxs-lookup"><span data-stu-id="825ba-147">Facts and Assertions</span></span>

<span data-ttu-id="825ba-148">Eftersom funktioner i Q# inte har några _logiska_ biverkningar kan andra _typer_ av effekter `()` av att köra en funktion vars utdatatyp är den tomma tuppeln aldrig observeras inifrån ett Q#-program.</span><span class="sxs-lookup"><span data-stu-id="825ba-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="825ba-149">Det innebär att en måldator kan välja `()` att inte köra någon funktion som returnerar med garantin att detta utelämnande inte kommer att ändra beteendet för någon följande Q#-kod.</span><span class="sxs-lookup"><span data-stu-id="825ba-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="825ba-150">Detta gör funktioner `()` som returnerar `Unit`(dvs. ) ett användbart verktyg för att bädda in påståenden och felsöka logik i Q#-program.</span><span class="sxs-lookup"><span data-stu-id="825ba-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="825ba-151">Låt oss överväga ett enkelt exempel:</span><span class="sxs-lookup"><span data-stu-id="825ba-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="825ba-152">Här anger `fail` nyckelordet att beräkningen inte ska fortsätta, vilket höjer ett undantag i måldatorn som kör Q#-programmet.</span><span class="sxs-lookup"><span data-stu-id="825ba-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="825ba-153">Per definition kan ett fel av detta slag inte observeras inifrån Q#, eftersom ingen ytterligare Q#-kod körs efter att en `fail` sats har nåtts.</span><span class="sxs-lookup"><span data-stu-id="825ba-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="825ba-154">Om vi går förbi en `PositivityFact`uppmaning till kan vi därför vara säkra på att dess bidrag var positivt.</span><span class="sxs-lookup"><span data-stu-id="825ba-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="825ba-155">Observera att vi kan implementera `PositivityFact` samma [`Fact`](xref:microsoft.quantum.diagnostics.fact) beteende <xref:microsoft.quantum.diagnostics> som att använda funktionen från namnområdet:</span><span class="sxs-lookup"><span data-stu-id="825ba-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="825ba-156">*Påståenden*, å andra sidan, används på samma sätt som fakta, men kan vara beroende av tillståndet för målmaskinen.</span><span class="sxs-lookup"><span data-stu-id="825ba-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="825ba-157">På motsvarande sätt definieras de som operationer, medan fakta definieras som funktioner (enligt ovan).</span><span class="sxs-lookup"><span data-stu-id="825ba-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="825ba-158">För att förstå skillnaden, överväga följande användning av ett faktum i ett påstående:</span><span class="sxs-lookup"><span data-stu-id="825ba-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="825ba-159">Här använder vi operationen <xref:microsoft.quantum.environment.getqubitsavailabletouse> för att returnera antalet qubits tillgängliga att använda.</span><span class="sxs-lookup"><span data-stu-id="825ba-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="825ba-160">Eftersom detta helt klart beror på det globala tillståndet i `AssertQubitsAreAvailable` programmet och dess genomförande miljö, måste vår definition av vara en operation också.</span><span class="sxs-lookup"><span data-stu-id="825ba-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="825ba-161">Vi kan dock använda det globala `Bool` tillståndet för att `Fact` ge ett enkelt värde som indata till funktionen.</span><span class="sxs-lookup"><span data-stu-id="825ba-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="825ba-162">Bygger på dessa idéer, erbjuder [förspelet](xref:microsoft.quantum.libraries.standard.prelude) två <xref:microsoft.quantum.intrinsic.assert> särskilt <xref:microsoft.quantum.intrinsic.assertprob> användbara påståenden, `()`och båda modelleras som operationer på .</span><span class="sxs-lookup"><span data-stu-id="825ba-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="825ba-163">Dessa påståenden tar var och en en Pauli-operatör som beskriver en viss mätning av intresse, ett kvantregister på vilket en mätning ska utföras och ett hypotetiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="825ba-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="825ba-164">På målmaskiner som fungerar genom simulering är vi inte bundna av [no-kloning sats](https://en.wikipedia.org/wiki/No-cloning_theorem), och kan utföra sådana mätningar utan att störa registret skickas till sådana påståenden.</span><span class="sxs-lookup"><span data-stu-id="825ba-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="825ba-165">En simulator kan sedan, `PositivityFact` liknande funktionen ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i praktiken:</span><span class="sxs-lookup"><span data-stu-id="825ba-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="825ba-166">På fysisk kvanthårdvara, där no-kloning sats förhindrar `Assert` undersökning `AssertProb` av `()` kvanttillstånd, och verksamheten helt enkelt tillbaka med någon annan effekt.</span><span class="sxs-lookup"><span data-stu-id="825ba-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="825ba-167">Namnområdet <xref:microsoft.quantum.diagnostics> ger flera fler `Assert` funktioner i familjen som gör det möjligt för oss att kontrollera mer avancerade förhållanden.</span><span class="sxs-lookup"><span data-stu-id="825ba-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="825ba-168">Dumpa funktioner</span><span class="sxs-lookup"><span data-stu-id="825ba-168">Dump Functions</span></span>

<span data-ttu-id="825ba-169">För att felsöka kvantprogram erbjuder <xref:microsoft.quantum.diagnostics> namnområdet två funktioner som kan dumpa i <xref:microsoft.quantum.diagnostics.dumpmachine> en <xref:microsoft.quantum.diagnostics.dumpregister>fil målmaskinens aktuella status: och .</span><span class="sxs-lookup"><span data-stu-id="825ba-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="825ba-170">Den genererade utgången för varje beror på målmaskinen.</span><span class="sxs-lookup"><span data-stu-id="825ba-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="825ba-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="825ba-171">DumpMachine</span></span>

<span data-ttu-id="825ba-172">Den fullständiga kvantsimulatorn distribueras som en del av Quantum Development Kit skriver in i filen [vågfunktionen](https://en.wikipedia.org/wiki/Wave_function) i hela kvantsystemet, som en endimensionell array av komplexa tal, där varje element representerar amplituden för sannolikheten för att mäta beräkningsbastillståndet $\ket{n}$, där $\ket{n} = \ket{b_{n-1}... b_1b_0} $ för bitar\{$ b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="825ba-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="825ba-173">På en dator med endast två qubits som tilldelats och i kvanttillståndet $$ \begin{align}{1}\ket{\psi} ={2}\frac {\sqrt } \ket{00} - \frac{(1 +{2} i)} \ket{10}genererar \end{align} $$-anropet <xref:microsoft.quantum.diagnostics.dumpmachine> den här utdata:</span><span class="sxs-lookup"><span data-stu-id="825ba-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="825ba-174">Den första raden ger en kommentar med ID:na för motsvarande qubits i deras betydande ordning.</span><span class="sxs-lookup"><span data-stu-id="825ba-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="825ba-175">Resten av raderna beskriver sannolikhetsamplituden för att mäta bastillståndsvektorn $\ket{n}$ i både kartesiska och polära format.</span><span class="sxs-lookup"><span data-stu-id="825ba-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="825ba-176">I detalj för den första raden:</span><span class="sxs-lookup"><span data-stu-id="825ba-176">In detail for the first row:</span></span>

* <span data-ttu-id="825ba-177">**`∣0❭:`** detta rad motsvarar `0` den beräkningsmässiga bastillståndet</span><span class="sxs-lookup"><span data-stu-id="825ba-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="825ba-178">**`0.707107 +  0.000000 i`**: sannolikhetsamplituden i kartesiskt format.</span><span class="sxs-lookup"><span data-stu-id="825ba-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="825ba-179">**` == `**: `equal` tecknet avslöjer båda likvärdiga representationer.</span><span class="sxs-lookup"><span data-stu-id="825ba-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="825ba-180">**`**********  `**: En grafisk representation av magnituden, antalet `*` står i proportion till sannolikheten för att mäta denna tillståndsvektor.</span><span class="sxs-lookup"><span data-stu-id="825ba-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="825ba-181">**`[ 0.500000 ]`**: det numeriska värdet av magnituden</span><span class="sxs-lookup"><span data-stu-id="825ba-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="825ba-182">**`    ---`**: En grafisk representation av amplitudens fas (se nedan).</span><span class="sxs-lookup"><span data-stu-id="825ba-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="825ba-183">**`[ 0.0000 rad ]`**: fasens numeriska värde (i radianer).</span><span class="sxs-lookup"><span data-stu-id="825ba-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="825ba-184">Både magnituden och fasen visas med en grafisk representation.</span><span class="sxs-lookup"><span data-stu-id="825ba-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="825ba-185">Magnitud representationen är rakt fram: det `*`visar en bar av , desto större sannolikhet desto större kommer stapeln att bli.</span><span class="sxs-lookup"><span data-stu-id="825ba-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="825ba-186">För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:</span><span class="sxs-lookup"><span data-stu-id="825ba-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="825ba-187">Följande exempel `DumpMachine` visas för några vanliga tillstånd:</span><span class="sxs-lookup"><span data-stu-id="825ba-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="825ba-188">Id för en qubit tilldelas vid körning och det är inte nödvändigtvis i linje med den ordning i vilken qubit tilldelades eller dess position inom en qubit register.</span><span class="sxs-lookup"><span data-stu-id="825ba-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="825ba-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="825ba-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="825ba-190">Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en brytpunkt i koden och inspektera värdet för en qubit-variabel, till exempel:</span><span class="sxs-lookup"><span data-stu-id="825ba-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![visa qubit id i Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="825ba-192">qubit med `0` index `register2` på har`3`id= , `1` qubit`2`med index har id = .</span><span class="sxs-lookup"><span data-stu-id="825ba-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="825ba-193">Kommandorad/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="825ba-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="825ba-194">Du kan räkna ut ett qubit-ID med hjälp av <xref:microsoft.quantum.intrinsic.message> funktionen och skicka qubit-variabeln i meddelandet, till exempel:</span><span class="sxs-lookup"><span data-stu-id="825ba-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="825ba-195">som skulle kunna generera denna produktion:</span><span class="sxs-lookup"><span data-stu-id="825ba-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="825ba-196">vilket innebär att qubit `0` `register2` med index`3`på har id `1` = ,`2`qubit med index har id = .</span><span class="sxs-lookup"><span data-stu-id="825ba-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="825ba-197"><xref:microsoft.quantum.diagnostics.dumpmachine>är en <xref:microsoft.quantum.diagnostics> del av namnområdet, så för att `open` kunna använda det måste du lägga till en sats:</span><span class="sxs-lookup"><span data-stu-id="825ba-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="825ba-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="825ba-198">DumpRegister</span></span>

<span data-ttu-id="825ba-199"><xref:microsoft.quantum.diagnostics.dumpregister>fungerar <xref:microsoft.quantum.diagnostics.dumpmachine>som , förutom att det också tar en rad qubits att begränsa mängden information till endast det som är relevant för motsvarande qubits.</span><span class="sxs-lookup"><span data-stu-id="825ba-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="825ba-200">Som <xref:microsoft.quantum.diagnostics.dumpmachine>med beror den <xref:microsoft.quantum.diagnostics.dumpregister> information som genereras av på målmaskinen.</span><span class="sxs-lookup"><span data-stu-id="825ba-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="825ba-201">För full-state quantum simulator det skriver in i filen vågen funktion upp till en global fas av quantum <xref:microsoft.quantum.diagnostics.dumpmachine>delsystem som genereras av de medföljande qubits i samma format som .</span><span class="sxs-lookup"><span data-stu-id="825ba-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="825ba-202">Till exempel{1}kan ta igen en maskin med endast två qubits tilldelas och i kvanttillstånd $$ \begin{align} \ket{\psi} = \frac {\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket `qubit[0]` {1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ som kräver <xref:microsoft.quantum.diagnostics.dumpregister> genererar den här utdatan:</span><span class="sxs-lookup"><span data-stu-id="825ba-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="825ba-203">och <xref:microsoft.quantum.diagnostics.dumpregister> kräver `qubit[1]` genererar denna utgång:</span><span class="sxs-lookup"><span data-stu-id="825ba-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="825ba-204">I allmänhet är tillståndet för ett register som är insnärjt med ett annat register ett blandat tillstånd snarare än en ren stat.</span><span class="sxs-lookup"><span data-stu-id="825ba-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="825ba-205">I det <xref:microsoft.quantum.diagnostics.dumpregister> här fallet matar ut följande meddelande:</span><span class="sxs-lookup"><span data-stu-id="825ba-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="825ba-206">I följande exempel visas hur <xref:microsoft.quantum.diagnostics.dumpregister> du <xref:microsoft.quantum.diagnostics.dumpmachine> kan använda både och i din Q#-kod:</span><span class="sxs-lookup"><span data-stu-id="825ba-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="825ba-207">Felsökning</span><span class="sxs-lookup"><span data-stu-id="825ba-207">Debugging</span></span>

<span data-ttu-id="825ba-208">Utöver `Assert` funktioner `Dump` och åtgärder stöder Q# en delmängd av standardfunktionerna för felsökning av Visual Studio: [ange radbrytningspunkter,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [stegning av kod med F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [inspektionsvärden för klassiska variabler](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) är alla möjliga under kodkörning på simulatorn.</span><span class="sxs-lookup"><span data-stu-id="825ba-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="825ba-209">Felsökning i Visual Studio-kod utnyttjar felsökningsfunktionerna i tillägget C# för Visual Studio-kod som drivs av OmniSharp och kräver installation av den [senaste versionen](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="825ba-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
