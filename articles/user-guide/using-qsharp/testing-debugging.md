---
title: Testa och felsöka
description: Lär dig hur du använder enhets tester, fakta och intyg och dumpa funktioner för att testa och felsöka Quantum-program.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630033"
---
# <a name="testing-and-debugging"></a>Testa och felsöka

Precis som med klassisk programmering är det viktigt att kunna kontrol lera att Quantum-programmen fungerar som avsett och att kunna diagnostisera ett Quantum-program som är felaktigt.
I det här avsnittet tar vi upp de verktyg som erbjuds av Q # för testning och fel sökning av Quantum-program.

## <a name="unit-tests"></a>Enhets tester

En vanlig metod för att testa klassiska program är att skriva små program som heter *enhets test* som kör kod i ett bibliotek och jämför dess utdata med förväntade utdata.
Vi kanske till exempel vill se till att `Square(2)` returer `4` , eftersom vi vet *en tidigare* version av $2 ^ 2 = $4.

Q # stöder skapande av enhets test för Quantum-program och som kan köras som tester i [xUnit](https://xunit.github.io/) unit test Framework.

### <a name="creating-a-test-project"></a>Skapa ett test projekt

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Öppna Visual Studio 2019. Gå till `File` menyn och välj `New`  >  `Project...` .
I det övre högra hörnet söker du efter `Q#` och väljer `Q# Test Project` mallen.

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Kör följande kommando från din favorit kommando rad:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Det nya projektet kommer att ha en enda fil `Tests.qs` som ger en praktisk plats för att definiera nya Q # Unit-tester.
Den här filen innehåller en prov enhets test `AllocateQubit` som kontrollerar att en nyligen allokerad qubit är i läget $ \ket {0} $ och skriver ut ett meddelande:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: ny: varje Q #-åtgärd eller funktion som tar ett argument av typen `Unit` och returer `Unit` kan markeras som ett enhets test via `@Test("...")` attributet. Argumentet till attributet `"QuantumSimulator"` ovan anger målet som testet körs på. Ett enda test kan köras på flera mål. Lägg till exempel till ett attribut `@Test("ResourcesEstimator")` ovan `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Spara filen och kör alla tester. Det bör nu finnas två enhets test, en där AllocateQubit körs på QuantumSimulator och en där den körs i ResourceEstimator. 

I Q #-kompilatorn identifieras de inbyggda målen "QuantumSimulator", "ToffoliSimulator" och "ResourcesEstimator" som giltiga körnings mål för enhets tester. Det är också möjligt att ange ett fullständigt kvalificerat namn för att definiera ett anpassat körnings mål. 

### <a name="running-q-unit-tests"></a>Köra Q # enhets test

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Som en konfiguration per lösning går du till `Test` menyn och väljer `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> Standardinställning för processor arkitektur för Visual Studio lagras i lösnings alternativ ( `.suo` )-filen för varje lösning.
> Om du tar bort den här filen måste du välja `X64` som processor arkitektur igen.

Bygg projektet, gå till `Test` menyn och välj `Windows`  >  `Test Explorer` . `AllocateQubit`visas i listan med tester i `Not Run Tests` gruppen. Välj `Run All` eller kör det här enskilda testet och det bör pass!

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Om du vill köra tester navigerar du till projektmappen (mappen som innehåller `Tests.csproj` ) och kör kommandot:

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

Enhets test kan filtreras efter namn och/eller körnings mål:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Den inbyggda funktionen <xref:microsoft.quantum.intrinsic.message> har typ `(String -> Unit)` och gör det möjligt att skapa diagnostiska meddelanden.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

När du har kört ett test i test Utforskaren och klickar på testet visas en panel med information om testkörning: status för skickad/misslyckad, förfluten tid och en "utdata"-länk. Om du klickar på länken "utdata" öppnas test resultatet i ett nytt fönster.

![testa utdata](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Status för pass/misslyckande för varje test skrivs ut till-konsolen av `dotnet test` .
Vid misslyckade tester skrivs utdata också ut till-konsolen för att hjälpa till att diagnostisera felet.

***

## <a name="facts-and-assertions"></a>Fakta och intyg

Eftersom funktioner i Q # inte har några _logiska_ sid effekter, kan alla _andra typer_ av effekter av att köra en funktion vars datatyp är den tomma tuppeln `()` aldrig observeras i ett Q #-program.
Det vill säga att mål datorn kan välja att inte köra någon funktion som returnerar `()` med garantin att detta utelämnande inte ändrar beteendet för någon av följande Q #-koder.
Detta gör att funktioner returnerar `()` (d.v.s. `Unit` ) ett användbart verktyg för att bädda in kontroller och fel söknings logik i Q #-program. 

Vi ska tänka på ett enkelt exempel:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Här anger nyckelordet `fail` att beräkningen inte ska fortsätta, vilket ger upphov till ett undantag på mål datorn som kör Q #-programmet.
Efter definition kan ett problem av den här typen inte observeras inifrån Q # eftersom ingen ytterligare Q # kod körs när en `fail` instruktion har nåtts.
På så sätt kan vi, om vi fortsätter med ett anrop till `PositivityFact` , säkerställa att dess inaktuella inaktuella värde var positiv.

Observera att vi kan implementera samma beteende som att `PositivityFact` använda [`Fact`](xref:microsoft.quantum.diagnostics.fact) funktionen från <xref:microsoft.quantum.diagnostics> namn området:

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

*Kontroller*, å andra sidan, används på liknande sätt som fakta, men kan vara beroende av mål datorns tillstånd. På motsvarande sätt definieras de som åtgärder, medan fakta definieras som funktioner (som ovan).
För att förstå skillnaden bör du överväga följande användning av ett faktum i en kontroll:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Här använder vi åtgärden <xref:microsoft.quantum.environment.getqubitsavailabletouse> för att returnera antalet qubits som kan användas.
Eftersom detta tydligt beror på programmets globala tillstånd och dess körnings miljö, så måste definitionen av `AssertQubitsAreAvailable` vara en åtgärd också.
Vi kan dock använda det globala läget för att ge ett enkelt `Bool` värde som inmatat för `Fact` funktionen.

[Inledning](xref:microsoft.quantum.libraries.standard.prelude) erbjuder två särskilt användbara intyg <xref:microsoft.quantum.intrinsic.assert> och <xref:microsoft.quantum.intrinsic.assertprob> båda modellerade som-åtgärder på `()` . Dessa intyg var och en tar en Pauli-operatör som beskriver en viss värdering av intresse, ett Quantum-register som en mätning ska utföras på och ett hypotetiskt resultat.
På mål datorer som arbetar med simuleringen är vi inte kopplade till [no-kloning-satsen](https://en.wikipedia.org/wiki/No-cloning_theorem)och kan utföra sådana mätningar utan att störa registret som skickats till sådana kontroller.
En simulator kan sedan, precis som `PositivityFact` funktionen ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i övningen:

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

På fysisk Quantum-maskinvara där ingen-kloning-satsen förhindrar granskning av Quantum-tillstånd, `Assert` returnerar och fungerar `AssertProb` åtgärderna bara `()` utan någon annan påverkan.

<xref:microsoft.quantum.diagnostics>Namn området innehåller flera fler funktioner i `Assert` familjen som gör det möjligt för oss att kontrol lera mer avancerade villkor. 

## <a name="dump-functions"></a>Dumpa funktioner

För att hjälpa till att felsöka Quantum-program <xref:microsoft.quantum.diagnostics> innehåller namn området två funktioner som kan dumpa till en fil aktuella status för mål datorn: <xref:microsoft.quantum.diagnostics.dumpmachine> och <xref:microsoft.quantum.diagnostics.dumpregister> . De utdata som genereras av var och en beror på mål datorn.

### <a name="dumpmachine"></a>DumpMachine

Den fullständiga Quantum-simulatorn som distribueras som en del av Quantum Development Kit skriver till filen [Wave-funktionen](https://en.wikipedia.org/wiki/Wave_function) i hela Quantum-systemet, som en endimensionell matris med komplexa tal, där varje element representerar amplituden av sannolikheten för att mäta beräknings bas status $ \ket{n} $, där $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ för BITS $ \{ b_i \} $. Till exempel på en dator som bara har två qubits tilldelade och i Quantum-tillstånd $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} genererar \end{align} $ $ anrop <xref:microsoft.quantum.diagnostics.dumpmachine> följande utdata:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.
Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{n} $ i båda formaten kartesiska och Polar. I detalj för den första raden:

* **`∣0❭:`** den här raden motsvarar `0` beräknings bas läget
* **`0.707107 +  0.000000 i`**: sannolikheten amplitud i kartesiska-format.
* **` == `**: `equal` tecknet separerar båda motsvarande representationer.
* **`**********  `**: En grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta den här tillstånds vektorn.
* **`[ 0.500000 ]`**: det numeriska värdet för storlek
* **`    ---`**: En grafisk representation av amplitudens fas (se nedan).
* **`[ 0.0000 rad ]`**: det numeriska värdet för fasen (i radianer).

Både storleken och fasen visas med en grafisk representation. Representation av storlek är rakt framåt: det visar ett fält med `*` , desto större sannolikhet desto större är stapeln. För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:

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

Följande exempel visar `DumpMachine` för några vanliga tillstånd:

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


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en Bryt punkt i koden och inspektera värdet för en qubit-variabel, till exempel:
  > 
  > ![Visa qubit-ID i Visual Studio](~/media/qubit_id.png)
  >
  > qubit med index `0` on `register2` har ID = `3` , qubit med index `1` har ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID med hjälp av <xref:microsoft.quantum.intrinsic.message> funktionen och skicka qubit-variabeln i meddelandet, till exempel:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > vilket kan generera följande utdata:
  >```
  > 0=q:3; 1=q:2
  >```
  > vilket innebär att qubit med index `0` on `register2` har ID = `3` , qubit med index `1` har ID = `2` .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>är en del av <xref:microsoft.quantum.diagnostics> namn området, så för att kunna använda det måste du lägga till en `open` instruktion:

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

<xref:microsoft.quantum.diagnostics.dumpregister>det fungerar som <xref:microsoft.quantum.diagnostics.dumpmachine> , förutom att det också tar en matris med qubits att begränsa den mängd information som är relevant för motsvarande qubits.

Precis som med är <xref:microsoft.quantum.diagnostics.dumpmachine> den information som genereras av <xref:microsoft.quantum.diagnostics.dumpregister> beroende av mål datorn. För den fulla tillstånds Quantum simulatorn skriver den till filen Wave-funktionen till en global fas av det Quantum-underordnade systemet som genererats av den angivna qubits i samma format som <xref:microsoft.quantum.diagnostics.dumpmachine> .  Till exempel ta en gång till en dator med endast två qubits tilldelade och i Quantum State $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ anrop <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[0]` genererar följande utdata:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

och anrop <xref:microsoft.quantum.diagnostics.dumpregister> för `qubit[1]` genererar följande utdata:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

I allmänhet är statusen för ett register som är Entangled med ett annat register blandat, i stället för ett rent tillstånd. I det här fallet ger <xref:microsoft.quantum.diagnostics.dumpregister> följande meddelande utdata:

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

I början av `Assert` och `Dump` Functions och Operations har Q # stöd för en delmängd av standard-fel söknings funktioner i Visual Studio: [ställa in rad Bryt punkter](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stega igenom kod med hjälp av F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [kontrol lera värden för klassiska variabler](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) är möjliga vid kod körning i simulatorn.

Fel sökning i Visual Studio Code utnyttjar de fel söknings funktioner som anges i C# för Visual Studio Code-tillägg som drivs av OmniSharp och som kräver installation av den [senaste versionen](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
