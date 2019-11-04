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
# <a name="testing-and-debugging"></a>Testning och fel sökning

Precis som med klassisk programmering är det viktigt att kunna kontrol lera att Quantum-programmen fungerar som avsett och att kunna diagnostisera ett Quantum-program som är felaktigt.
I det här avsnittet tar vi upp de verktyg som erbjuds av Q # för testning och fel sökning av Quantum-program.

## <a name="unit-tests"></a>Enhets tester

En vanlig metod för att testa klassiska program är att skriva små program som heter *enhets test* som kör kod i ett bibliotek och jämför dess utdata med förväntade utdata.
Vi kanske till exempel vill se till att `Square(2)` returnerar `4`, eftersom vi vet *en tidigare* version av $2 ^ 2 = $4.

Q # stöder skapande av enhets test för Quantum-program och som kan köras som tester i [xUnit](https://xunit.github.io/) unit test Framework.

### <a name="creating-a-test-project"></a>Skapa ett test projekt

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Öppna Visual Studio 2019. Gå till `File`-menyn och välj `New` > `Project...`.
Välj `Q# Test Project` mall under `Installed` > `Visual C#`i Utforskaren.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Kör följande kommando från din favorit kommando rad:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

I båda fallen kommer det nya projektet att ha två öppna filer.
Den första filen `Tests.qs`, är en lämplig plats för att definiera nya Q # Unit-tester.
Inlednings vis innehåller den här filen en test `AllocateQubitTest` som kontrollerar att en nyligen allokerad qubit är i läget $ \ket{0}$ och skriver ut ett meddelande:

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Alla Q #-åtgärder som är kompatibla med typen `(Unit => Unit)` eller funktionen som är kompatibla med `(Unit -> Unit)` kan köras som ett enhets test. 

Den andra filen `TestSuiteRunner.cs` innehåller en metod som används för att identifiera och köra Q # Unit-tester. Detta är metoden `TestTarget` som är kommenterad med `OperationDriver` attribut.
`OperationDriver`-attributet ingår i Xunit-tilläggs biblioteket Microsoft. Quantum. simulering. Xunit.
Enhets test ramverket anropar `TestTarget` metod för varje Q # enhets test som har identifierats.
Ramverket skickar beskrivningen av enhets test till metoden via `op` argument. Följande kodrad:
```csharp
op.TestOperationRunner(sim);
```
Kör enhets testet på `QuantumSimulator`.

Som standard söker mekanismen för enhets test identifiering efter alla Q #-funktioner eller-åtgärder av kompatibel typ som uppfyller följande egenskaper:
* Placeras i samma sammansättning som metoden som är kommenterad med `OperationDriver`-attributet.
* Finns i samma namnrymd som metoden som är kommenterad med `OperationDriver`-attributet.
* Har ett namn som slutar med `Test`.

En sammansättning, ett namn område och ett suffix för enhets test funktioner och åtgärder kan anges med valfria parametrar för attributet `OperationDriver`:
* `AssemblyName` parameter anger namnet på sammansättningen som genomsöks efter tester.
* `TestNamespace` parameter anger namnet på namn området som söks efter tester.
* `Suffix` anger suffixet för åtgärds-eller funktions namn som anses vara enhets test.

Dessutom kan du med `TestCasePrefix` valfria parametern ange ett prefix för namnet på test ärendet. Prefixet framför åtgärds namnet visas i listan över test fall. `TestCasePrefix = "QSim:"` kan till exempel göra att `AllocateQubitTest` visas som `QSim:AllocateQubitTest` i listan med hittade tester. Detta kan vara användbart för att indikera till exempel vilken simulator som används för att köra ett test.

### <a name="running-q-unit-tests"></a>Köra Q # enhets test

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Som en konfiguration per lösning går du till `Test`-menyn och väljer `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> Standardinställningen för processor arkitektur för Visual Studio lagras i lösnings alternativ filen (`.suo`) för varje lösning.
> Om du tar bort den här filen måste du välja `X64` som processor arkitektur igen.

Bygg projektet, gå till `Test`-menyn och välj `Windows` > `Test Explorer`. `AllocateQubitTest` visas i listan med tester i `Not Run Tests`s gruppen. Välj `Run All` eller kör det här enskilda testet så bör det passas!

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Om du vill köra tester navigerar du till projektmappen (mappen som innehåller `Tests.csproj`) och kör kommandot:

```bash
$ dotnet restore
$ dotnet test
```

Du bör få utdata som liknar följande:

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

## <a name="logging-and-assertions"></a>Loggning och intyg

En viktig följd av det faktum att funktioner i Q # inte har några sido effekter är att alla effekter av att köra en funktion vars Utdatatyp är den tomma tuppeln `()` aldrig kan observeras i ett Q #-program.
Det innebär att en måldator kan välja att inte köra någon funktion som returnerar `()` med garantin att detta utelämnande inte ändrar beteendet för någon av följande Q #-koder.
Detta gör att funktioner returnerar `()` ett användbart verktyg för att bädda in kontroller och fel söknings logik i Q #-program. 

### <a name="logging"></a>Loggning

Den inbyggda funktionen <xref:microsoft.quantum.intrinsic.message> har typen `(String -> Unit)` och gör det möjligt att skapa diagnostiska meddelanden.

`onLog` åtgärden för `QuantumSimulator` kan användas för att definiera åtgärder som utförs när Q # Code-anrop `Message`. Som standard skrivs loggade meddelanden ut till standardutdata.

När du definierar en enhets tests Suite kan de loggade meddelandena dirigeras till test resultatet. När ett projekt skapas från en test projekt mal len för Q #, är denna omdirigering förkonfigurerad för sviten och skapas som standard enligt följande:

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

När du har kört ett test i test Utforskaren och klickar på testet visas en panel med information om testkörning: status för skickad/misslyckad, förfluten tid och en "utdata"-länk. Om du klickar på länken "utdata" öppnas test resultatet i ett nytt fönster.

![testa utdata](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Status för pass/misslyckande för varje test skrivs ut till-konsolen med `dotnet test`.
Vid misslyckade tester skrivs utdata som loggats till följd av `output.WriteLine(msg)` anropet ovan också till-konsolen för att hjälpa till att diagnostisera felet.

***

### <a name="assertions"></a>Intyg

Samma logik kan användas för att implementera kontroller. Vi ska tänka på ett enkelt exempel:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Här anger nyckelordet `fail` att beräkningen inte bör fortsätta, vilket ger upphov till ett undantag på mål datorn som kör Q #-programmet.
Efter definition kan ett problem av den här typen inte observeras inifrån Q # eftersom ingen ytterligare Q # kod körs när en `fail`-instruktion har nåtts.
Om vi fortsätter att passera ett anrop till `AssertPositive`, kan vi därför vara säkra på att dess inaktuella information var positiv.

[Inledning](xref:microsoft.quantum.libraries.standard.prelude) erbjuder två särskilt användbara kontroller, <xref:microsoft.quantum.intrinsic.assert> och <xref:microsoft.quantum.intrinsic.assertprob> både modellerade som åtgärder på `()`. Dessa intyg var och en tar en Pauli-operatör som beskriver en viss värdering av intresse, ett Quantum-register som en mätning ska utföras på och ett hypotetiskt resultat.
På mål datorer som arbetar med simuleringen är vi inte kopplade till [no-kloning-satsen](https://en.wikipedia.org/wiki/No-cloning_theorem)och kan utföra sådana mätningar utan att störa registret som skickats till sådana kontroller.
En simulator kan sedan, som liknar `AssertPositive` funktion ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i övningen:

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

På fysisk Quantum-maskinvara där ingen-kloning-satsen förhindrar granskning av Quantum-tillstånd, returnerar `Assert` och `AssertProb` åtgärder bara `()` utan någon annan påverkan.

<xref:microsoft.quantum.diagnostics>-namnrymden innehåller flera fler funktioner i `Assert`-serien som gör det möjligt för oss att kontrol lera mer avancerade villkor. 

## <a name="dump-functions"></a>Dumpa funktioner

För att hjälpa till att felsöka Quantum-program erbjuder <xref:microsoft.quantum.diagnostics>-namnrymden två funktioner som kan dumpa till en fil aktuella status för mål datorn: <xref:microsoft.quantum.diagnostics.dumpmachine> och <xref:microsoft.quantum.diagnostics.dumpregister>. De utdata som genereras av var och en beror på mål datorn.

### <a name="dumpmachine"></a>DumpMachine

Den fullständiga Quantum-simulatorn som distribueras som en del av Quantum Development Kit skriver till filen [Wave-funktionen](https://en.wikipedia.org/wiki/Wave_function) i hela Quantum-systemet, som en endimensionell matris med komplexa tal, där varje element representerar amplituden för sannolikhet för mätning av beräknings bas tillstånd $ \ket{n} $, där $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ för BITS $\{b_i\}$. Till exempel på en dator som bara har två qubits allokerade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpmachine> genererar dessa utdata :

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.
Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{n} $ i båda formaten kartesiska och Polar. I detalj för den första raden:

* **`∣0❭:`** den här raden motsvarar `0` beräknings bas status
* **`0.707107 +  0.000000 i`** : sannolikheten amplitud i kartesiska-format.
* **` == `** : `equal`-tecknet separerar både motsvarande representationer.
* **`**********  `** : en grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta denna tillstånds vektor.
* **`[ 0.500000 ]`** : det numeriska värdet för förstornas storlek
* **`    ---`** : en grafisk representation av amplitudens fas (se nedan).
* **`[ 0.0000 rad ]`** : det numeriska värdet för fasen (i radianer).

Både storleken och fasen visas med en grafisk representation. Representation av storlek är rak: det visar ett stapeldiagram med `*`desto större sannolikhet desto större stapel blir. För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:

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

I följande exempel visas `DumpMachine` för några vanliga tillstånd:

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
  > ID: t för en qubit tilldelas vid körning och är inte nödvändigt vis justerat i den ordning som qubit allokerades eller var i ett qubit-register.


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en Bryt punkt i koden och inspektera värdet för en qubit-variabel, till exempel:
  > 
  > ![Visa qubit-ID i Visual Studio](~/media/qubit_id.png)
  >
  > qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID med hjälp av funktionen <xref:microsoft.quantum.intrinsic.message> och skicka qubit-variabeln i meddelandet, till exempel:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > vilket kan generera följande utdata:
  >```
  > 0=q:3; 1=q:2
  >```
  > vilket innebär att qubit med index `0` på `register2` har ID =`3`, qubit med index `1` har ID =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> är en del av <xref:microsoft.quantum.diagnostics>-namnområdet så att du måste lägga till ett `open`-uttryck för att kunna använda det:

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


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> fungerar som <xref:microsoft.quantum.diagnostics.dumpmachine>, förutom att det också tar en matris med qubits för att begränsa den mängd information som är relevant för motsvarande qubits.

Precis som med <xref:microsoft.quantum.diagnostics.dumpmachine>är den information som genereras av <xref:microsoft.quantum.diagnostics.dumpregister> beroende av mål datorn. För den fulla tillstånds Quantum simulatorn skrivs den till filen Wave-funktionen till en global fas av det Quantum-underordnade systemet som genererats av den angivna qubits i samma format som <xref:microsoft.quantum.diagnostics.dumpmachine>.  Ta till exempel en dator med endast två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ anropa <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[0]` genererar följande utdata:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

och anropar <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[1]` genererar följande utdata:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

I allmänhet är statusen för ett register som är Entangled med ett annat register blandat, i stället för ett rent tillstånd. I det här fallet <xref:microsoft.quantum.diagnostics.dumpregister> utdata i följande meddelande:

```
Qubits provided (0;) are entangled with some other qubit.
```

I följande exempel visas hur du kan använda både <xref:microsoft.quantum.diagnostics.dumpregister> och <xref:microsoft.quantum.diagnostics.dumpmachine> i din Q #-kod:

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

## <a name="debugging"></a>Felsökning

Utöver `Assert` och `Dump` funktioner och åtgärder stöder Q # en delmängd av standard funktioner för Visual Studio-fel sökning: [Ange rad Bryt punkter](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stega genom kod med hjälp av F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [inspektera värden för klassiska variabler ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)är allt möjligt vid kod körning i simulatorn.

Det finns ännu inte stöd för fel sökning i Visual Studio Code.

