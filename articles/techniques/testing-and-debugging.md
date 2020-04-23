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
# <a name="testing-and-debugging"></a>Testning och felsökning

Som med klassisk programmering, är det viktigt att kunna kontrollera att kvantprogram fungerar som avsett, och att kunna diagnostisera ett kvantprogram som är felaktigt.
I det här avsnittet täcker vi de verktyg som erbjuds av Q# för testning och felsökning av kvantprogram.

## <a name="unit-tests"></a>Enhetstester

En vanlig metod för att testa klassiska program är att skriva små program som kallas *enhetstester* som kör kod i ett bibliotek och jämföra dess produktion till vissa förväntade produktionen.
Till exempel kanske vi vill `Square(2)` `4`se till att avkastningen , eftersom vi vet *a priori* att $ 2 ^ 2 = 4 $.

Q# stöder att skapa enhetstester för kvantprogram och som kan utföras som tester inom [testramverket för xUnit-enheten.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Skapa ett testprojekt

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Öppna Visual Studio 2019. Gå till `File` menyn `New`  >  `Project...`och välj .
Sök efter `Q#`i det övre högra `Q# Test Project` hörnet och välj mallen.

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Kör följande kommando på din favoritkommandorad:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Det nya projektet kommer `Tests.qs`att ha en enda fil, vilket ger en bekväm plats att definiera nya Q# enhetstester.
Inledningsvis den här filen innehåller `AllocateQubit` ett exempel enhet test som kontrollerar att en{0}nyligen allokerad qubit är i $\ket $ tillstånd och skriver ut ett meddelande:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:ny: Alla Q#-åtgärder eller -funktioner `Unit` som `Unit` tar ett argument av `@Test("...")` typ och returer kan markeras som ett enhetstest via attributet. Argumentet till det `"QuantumSimulator"` attributet anger det mål som testet körs på. Ett enda test kan utföras på flera mål. Lägg till exempel `@Test("ResourcesEstimator")` till `AllocateQubit`ett attribut ovan . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Spara filen och kör alla tester. Det bör nu finnas två enhetstester, en där AllocateQubit körs på QuantumSimulator och en där den körs i ResourceEstimator. 

Q# kompilatorn känner igen de inbyggda målen "QuantumSimulator", "ToffoliSimulator" och "ResourcesEstimator" som giltiga körningsmål för enhetstester. Det är också möjligt att ange alla fullständigt kvalificerade namn för att definiera ett anpassat körningsmål. 

### <a name="running-q-unit-tests"></a>Köra Q# enhetstester

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Som en engångsinställning per lösning går `Test` du `Test Settings`  >  `Default Processor Architecture`  >  `X64`till menyn och väljer .

> [!TIP]
> Standardinställningen för processorarkitektur för Visual Studio`.suo`lagras i lösningsalternativen ( ) för varje lösning.
> Om du tar bort den här `X64` filen måste du välja som processorarkitektur igen.

Bygg projektet, gå `Test` till menyn `Windows`  >  `Test Explorer`och välj . `AllocateQubit`visas i listan över tester `Not Run Tests` i gruppen. Välj `Run All` eller kör detta individuella test, och det bör passera!

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Om du vill köra tester navigerar du `Tests.csproj`till projektmappen (mappen som innehåller) och kör kommandot:

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

Enhetstester kan filtreras efter namn och/eller körningsmål:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Den inneboende <xref:microsoft.quantum.intrinsic.message> funktionen `(String -> Unit)` har typ och gör det möjligt att skapa diagnostiska meddelanden.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

När du har körat ett test i Test Explorer och klickat på testet visas en panel med information om testkörning: Godkänd/misslyckad status, förfluten tid och en "Utdata"-länk. Om du klickar på länken "Utdata" öppnas testutdata i ett nytt fönster.

![testutgång](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

Statusen godkänd/underkänd för varje test skrivs ut till konsolen av `dotnet test`.
För misslyckade tester skrivs ututgångarna också till konsolen för att diagnostisera felet.

***

## <a name="facts-and-assertions"></a>Fakta och påståenden

Eftersom funktioner i Q# inte har några _logiska_ biverkningar kan andra _typer_ av effekter `()` av att köra en funktion vars utdatatyp är den tomma tuppeln aldrig observeras inifrån ett Q#-program.
Det innebär att en måldator kan välja `()` att inte köra någon funktion som returnerar med garantin att detta utelämnande inte kommer att ändra beteendet för någon följande Q#-kod.
Detta gör funktioner `()` som returnerar `Unit`(dvs. ) ett användbart verktyg för att bädda in påståenden och felsöka logik i Q#-program. 

Låt oss överväga ett enkelt exempel:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Här anger `fail` nyckelordet att beräkningen inte ska fortsätta, vilket höjer ett undantag i måldatorn som kör Q#-programmet.
Per definition kan ett fel av detta slag inte observeras inifrån Q#, eftersom ingen ytterligare Q#-kod körs efter att en `fail` sats har nåtts.
Om vi går förbi en `PositivityFact`uppmaning till kan vi därför vara säkra på att dess bidrag var positivt.

Observera att vi kan implementera `PositivityFact` samma [`Fact`](xref:microsoft.quantum.diagnostics.fact) beteende <xref:microsoft.quantum.diagnostics> som att använda funktionen från namnområdet:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Påståenden*, å andra sidan, används på samma sätt som fakta, men kan vara beroende av tillståndet för målmaskinen. På motsvarande sätt definieras de som operationer, medan fakta definieras som funktioner (enligt ovan).
För att förstå skillnaden, överväga följande användning av ett faktum i ett påstående:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Här använder vi operationen <xref:microsoft.quantum.environment.getqubitsavailabletouse> för att returnera antalet qubits tillgängliga att använda.
Eftersom detta helt klart beror på det globala tillståndet i `AssertQubitsAreAvailable` programmet och dess genomförande miljö, måste vår definition av vara en operation också.
Vi kan dock använda det globala `Bool` tillståndet för att `Fact` ge ett enkelt värde som indata till funktionen.

Bygger på dessa idéer, erbjuder [förspelet](xref:microsoft.quantum.libraries.standard.prelude) två <xref:microsoft.quantum.intrinsic.assert> särskilt <xref:microsoft.quantum.intrinsic.assertprob> användbara påståenden, `()`och båda modelleras som operationer på . Dessa påståenden tar var och en en Pauli-operatör som beskriver en viss mätning av intresse, ett kvantregister på vilket en mätning ska utföras och ett hypotetiskt resultat.
På målmaskiner som fungerar genom simulering är vi inte bundna av [no-kloning sats](https://en.wikipedia.org/wiki/No-cloning_theorem), och kan utföra sådana mätningar utan att störa registret skickas till sådana påståenden.
En simulator kan sedan, `PositivityFact` liknande funktionen ovan, avbryta beräkningen om det hypotetiska resultatet inte skulle observeras i praktiken:

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

På fysisk kvanthårdvara, där no-kloning sats förhindrar `Assert` undersökning `AssertProb` av `()` kvanttillstånd, och verksamheten helt enkelt tillbaka med någon annan effekt.

Namnområdet <xref:microsoft.quantum.diagnostics> ger flera fler `Assert` funktioner i familjen som gör det möjligt för oss att kontrollera mer avancerade förhållanden. 

## <a name="dump-functions"></a>Dumpa funktioner

För att felsöka kvantprogram erbjuder <xref:microsoft.quantum.diagnostics> namnområdet två funktioner som kan dumpa i <xref:microsoft.quantum.diagnostics.dumpmachine> en <xref:microsoft.quantum.diagnostics.dumpregister>fil målmaskinens aktuella status: och . Den genererade utgången för varje beror på målmaskinen.

### <a name="dumpmachine"></a>DumpMachine

Den fullständiga kvantsimulatorn distribueras som en del av Quantum Development Kit skriver in i filen [vågfunktionen](https://en.wikipedia.org/wiki/Wave_function) i hela kvantsystemet, som en endimensionell array av komplexa tal, där varje element representerar amplituden för sannolikheten för att mäta beräkningsbastillståndet $\ket{n}$, där $\ket{n} = \ket{b_{n-1}... b_1b_0} $ för bitar\{$ b_i\}$. På en dator med endast två qubits som tilldelats och i kvanttillståndet $$ \begin{align}{1}\ket{\psi} ={2}\frac {\sqrt } \ket{00} - \frac{(1 +{2} i)} \ket{10}genererar \end{align} $$-anropet <xref:microsoft.quantum.diagnostics.dumpmachine> den här utdata:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Den första raden ger en kommentar med ID:na för motsvarande qubits i deras betydande ordning.
Resten av raderna beskriver sannolikhetsamplituden för att mäta bastillståndsvektorn $\ket{n}$ i både kartesiska och polära format. I detalj för den första raden:

* **`∣0❭:`** detta rad motsvarar `0` den beräkningsmässiga bastillståndet
* **`0.707107 +  0.000000 i`**: sannolikhetsamplituden i kartesiskt format.
* **` == `**: `equal` tecknet avslöjer båda likvärdiga representationer.
* **`**********  `**: En grafisk representation av magnituden, antalet `*` står i proportion till sannolikheten för att mäta denna tillståndsvektor.
* **`[ 0.500000 ]`**: det numeriska värdet av magnituden
* **`    ---`**: En grafisk representation av amplitudens fas (se nedan).
* **`[ 0.0000 rad ]`**: fasens numeriska värde (i radianer).

Både magnituden och fasen visas med en grafisk representation. Magnitud representationen är rakt fram: det `*`visar en bar av , desto större sannolikhet desto större kommer stapeln att bli. För fasen visar vi följande symboler för att representera vinkeln baserat på intervall:

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

Följande exempel `DumpMachine` visas för några vanliga tillstånd:

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
  > Id för en qubit tilldelas vid körning och det är inte nödvändigtvis i linje med den ordning i vilken qubit tilldelades eller dess position inom en qubit register.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID i Visual Studio genom att placera en brytpunkt i koden och inspektera värdet för en qubit-variabel, till exempel:
  > 
  > ![visa qubit id i Visual Studio](~/media/qubit_id.png)
  >
  > qubit med `0` index `register2` på har`3`id= , `1` qubit`2`med index har id = .

#### <a name="command-line--visual-studio-code"></a>[Kommandorad/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Du kan räkna ut ett qubit-ID med hjälp av <xref:microsoft.quantum.intrinsic.message> funktionen och skicka qubit-variabeln i meddelandet, till exempel:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > som skulle kunna generera denna produktion:
  >```
  > 0=q:3; 1=q:2
  >```
  > vilket innebär att qubit `0` `register2` med index`3`på har id `1` = ,`2`qubit med index har id = .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>är en <xref:microsoft.quantum.diagnostics> del av namnområdet, så för att `open` kunna använda det måste du lägga till en sats:

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

<xref:microsoft.quantum.diagnostics.dumpregister>fungerar <xref:microsoft.quantum.diagnostics.dumpmachine>som , förutom att det också tar en rad qubits att begränsa mängden information till endast det som är relevant för motsvarande qubits.

Som <xref:microsoft.quantum.diagnostics.dumpmachine>med beror den <xref:microsoft.quantum.diagnostics.dumpregister> information som genereras av på målmaskinen. För full-state quantum simulator det skriver in i filen vågen funktion upp till en global fas av quantum <xref:microsoft.quantum.diagnostics.dumpmachine>delsystem som genereras av de medföljande qubits i samma format som .  Till exempel{1}kan ta igen en maskin med endast två qubits tilldelas och i kvanttillstånd $$ \begin{align} \ket{\psi} = \frac {\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket `qubit[0]` {1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ som kräver <xref:microsoft.quantum.diagnostics.dumpregister> genererar den här utdatan:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

och <xref:microsoft.quantum.diagnostics.dumpregister> kräver `qubit[1]` genererar denna utgång:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

I allmänhet är tillståndet för ett register som är insnärjt med ett annat register ett blandat tillstånd snarare än en ren stat. I det <xref:microsoft.quantum.diagnostics.dumpregister> här fallet matar ut följande meddelande:

```
Qubits provided (0;) are entangled with some other qubit.
```

I följande exempel visas hur <xref:microsoft.quantum.diagnostics.dumpregister> du <xref:microsoft.quantum.diagnostics.dumpmachine> kan använda både och i din Q#-kod:

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

Utöver `Assert` funktioner `Dump` och åtgärder stöder Q# en delmängd av standardfunktionerna för felsökning av Visual Studio: [ange radbrytningspunkter,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [stegning av kod med F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) och [inspektionsvärden för klassiska variabler](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) är alla möjliga under kodkörning på simulatorn.

Felsökning i Visual Studio-kod utnyttjar felsökningsfunktionerna i tillägget C# för Visual Studio-kod som drivs av OmniSharp och kräver installation av den [senaste versionen](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). 
