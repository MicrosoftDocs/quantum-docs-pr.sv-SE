---
title: Kvantgrunder med Q#
description: Lär dig hur man skriver ett kvantprogram i Q#. Utveckla ett Bell-tillståndsprogram med Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 30135fa8a123e52a92b7187218f9980ba3cdbd2d
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442209"
---
# <a name="quantum-basics-with-q"></a>Kvantgrunder med Q#

I den här snabbstarten visar vi hur du skriver ett Q#-program som ändrar och mäter kvantbitar, samt visar effekterna av superposition och sammanflätning.  Du får hjälp med att installera QDK, skapa programmet och köra programmet på en kvantsimulator.  

Du kommer att skriva ett program med namnet Bell som visar kvantsammanflätning.  Namnet Bell syftar på Bell-tillstånd, vilket är specifika kvanttillstånd för två kvantbitar som används för att visa de enklaste exemplen på superposition och kvantsammanflätning. 

## <a name="pre-requisites"></a>Förutsättningar

Om du är redo att börja koda följer du nedanstående steg innan du fortsätter: 

* [Installera](xref:microsoft.quantum.install) Quantum Development Kit för det språk och den utvecklingsmiljö som du använder
* Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen

Du kan också följa med i texten utan att installera QDK. Du får då en översikt över Q#-programmeringsspråket och de första begreppen inom kvantberäkning.

## <a name="demonstrating-qubit-behavior-with-q"></a>Demonstrera kvantbitsbeteende med Q#

Kommer du ihåg vår enkla [definition av en kvantbit](xref:microsoft.quantum.overview.what#the-qubit)?  Där klassiska bitar innehåller ett enda binärt värde av 0 eller 1, kan tillståndet för en kvantbit vara i en **superposition** med 0 och 1 samtidigt.  Begreppsmässigt kan man tänka på en kvantbit som en riktning (kallas även för vektor).  En kvantbit kan ha någon av de riktningar som är möjliga. De två **klassiska tillstånden** är två riktningar. De motsvarar en chans på 100 % att mäta 0 och en chans på 100 % att mäta 1.  Detta kan även visualiseras med [Bloch-sfären](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere).


Mätningen genererar ett binärt resultat och ändrar kvantbitens tillstånd. Mätningen genererar ett binärt värde, antingen 0 eller 1.  Kvantbiten går från att vara i superposition (vilken riktning som helst) till ett av de klassiska tillstånden.  När du därefter upprepar samma mätning utan några andra åtgärder får du samma binära resultat.  

Flera kvantbitar kan vara **sammanflätade**. När vi mäter en sammanflätad kvantbit får vi även veta de andra kvantbitarnas tillstånd.

Nu är vi redo att demonstrera hur Q# uttrycker detta beteende.  Du börjar med det enklaste programmet och skapar det för att visa en kvantsuperposition och kvantsammanflätning.

## <a name="setup"></a>Konfiguration

Program som har utvecklats med Microsofts Quantum Development Kit består av två delar:

1. En eller flera kvantalgoritmer som har implementerats med hjälp av kvantprogrammeringsspråket Q#.
1. Ett värdprogram som har implementerats i ett programmeringsspråk som Python eller C#, som fungerar som huvudstartpunkt och som anropar Q#-åtgärder för att köra en kvantalgoritm.

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Välj en plats för ditt program

1. Skapa en fil med namnet `Bell.qs`. Filen kommer att innehålla din Q#-kod.

1. Skapa en fil med namnet `host.py`. Filen kommer att innehålla din Python-värdkod.

#### <a name="c-command-linetabtabid-csharp"></a>[C#-kommandorad](#tab/tabid-csharp).

1. Skapa ett nytt Q#-projekt:

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Du bör se en `.csproj`-fil, en Q#-fil som heter `Operations.qs` och en värdprogramfil som heter `Driver.cs`

1. Byt namn på Q#-filen

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studiotabtabid-vs2019"></a>[Visual Studio](#tab/tabid-vs2019)

1. Skapa ett nytt projekt

   * Öppna Visual Studio
   * Gå till menyn **Arkiv** och välj **Nytt** -> **Projekt...**
   * I projektmallens utforskare skriver du `Q#` i sökfältet och väljer mallen `Q# Application`
   * Ge ditt projekt namnet `Bell`

1. Byt namn på Q#-filen

   * Gå till **Solution Explorer**
   * Högerklicka på `Operations.qs`-filen
   * Byt namn på den till `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>Skriv en Q#-åtgärd

Vårt mål är att förbereda två kvantbitar i ett särskilt kvanttillstånd, demonstrera hur du använder kvantbitar med Q# för att ändra deras tillstånd, samt demonstrera effekterna av superposition och sammanflätning. Vi kommer att bygga upp detta bit för bit för att visa kvantbitarnas tillstånd, åtgärder och mätning.

**Översikt:**  I den första koden nedan visar vi dig hur man arbetar med kvantbitar i Q#.  Vi visar två åtgärder, `M` och `X`, som omvandlar tillståndet för en kvantbit. 

I det här kodfragmentet definieras åtgärden `Set` som använder en parameter som kvantbit och en annan parameter, `desired`, som representerar det tillstånd som vi vill att kvantbiten ska ha.  Åtgärden `Set` utför en mätning på kvantbiten med åtgärden `M`.  I Q# returnerar en kvantbitsmätning alltid antingen `Zero` eller `One`.  Om mätningen returnerar ett värde som inte är lika med det önskade värdet, anger du att kvantbiten ska ”vändas”. Det innebär att den kör en `X`-åtgärd som ändrar kvantbitens tillstånd till ett nytt tillstånd där sannolikheten för att en mätning ska returnera `Zero` och `One` är omvänd.  En `TestBellState`-åtgärd läggs till för att demonstrera resultatet av åtgärden `Set`.  Den här åtgärden tar `Zero` eller `One` som indata och anropar `Set`-åtgärden ett visst antal gånger med indatan. Därefter räknas det antal gånger som `Zero` returnerades från kvantbitsmätningen och antalet gånger som `One` returnerades. I den här första simuleringen av `TestBellState`-åtgärden förväntar vi oss givetvis att utdatan ska visa att alla mätningar av kvantbitsuppsättningen med `Zero` som parameterindata ska returnera `Zero`, och att alla mätningar av en kvantbitsuppsättning med `One` som parameterindata ska returnera `One`.  Senare kommer vi att lägga till kod i `TestBellState` som demonstrerar superposition och sammanflätning.


### <a name="q-operation-code"></a>Q#-åtgärdskod

1. Ersätt innehållet i filen Bells.qs med följande kod:

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

    Den här åtgärden kan nu anropas för att försätta en kvantbit i ett klassiskt tillstånd som antingen returnerar `Zero` 100 % av tiden eller `One` 100 % av tiden.  `Zero` och `One` är konstanter som representerar de enda två möjliga resultaten från en kvantbitsmätning.

    Åtgärden `Set` mäter kvantbiten.
    Om kvantbiten är i det tillstånd som vi vill ha, lämnar `Set` den oförändrad. Annars ändrar vi kvantbitens tillstånd till önskat tillstånd genom att köra åtgärden `X`.

### <a name="about-q-operations"></a>Om Q#-åtgärder

En Q#-åtgärd är en kvantsubrutin. Det innebär att det är en anropningsbar rutin som innehåller kvantåtgärder.

Argumenten i en åtgärd anges som en tuppel inom parentes.

Returtypen för åtgärden anges efter ett kolon. I det här fallet saknar `Set`-åtgärden en retur, så den markeras som en retur för `Unit`. Detta är Q#-motsvarigheten till `unit` i F#, vilket är ungefär detsamma som `void` i C# och en tom tuppel (`Tuple[()]`) i Python.

Du använde två kvantåtgärder i din första Q#-åtgärd:

* [M](xref:microsoft.quantum.intrinsic.m)-åtgärden som mäter kvantbitens tillstånd
* [X](xref:microsoft.quantum.intrinsic.x)-åtgärden som vänder kvantbitens tillstånd

En kvantåtgärd omvandlar tillståndet för en kvantbit. Ibland pratar man om kvantgrindar i stället för åtgärder, vilket motsvarar klassiska logiska grindar. Detta kommer från när man började använda kvantberäkning och algoritmerna bara var en teoretisk konstruktion som visualiserades som diagram, liknande kretsdiagram i klassisk databehandling.

### <a name="add-q-test-code"></a>Lägg till testkod för Q#

1. Lägg till följande åtgärd i `Bell.qs`-filen (inuti namnområdet) efter att `Set`-åtgärden har slutförts:

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

    Åtgärden (`TestBellState`) kommer att upprepas för `count` iterationer, ange ett angivet `initial`-värde för en kvantbit och sedan mäta (`M`) resultatet. Den samlar in statistik om hur många nollor och ettor som vi har mätt och returnerar dem till anroparen. Den utför även en annan åtgärd som krävs. Den återställer kvantbiten till ett känt tillstånd (`Zero`) innan den returnerar, så att andra kan allokera kvantbiten i ett känt tillstånd. Detta krävs av `using`-instruktionen.

### <a name="about-variables-in-q"></a>Om variabler i Q#

Som standard är variablerna i Q# oföränderliga. Värdet kan inte ändras efter att de har bundits. Nyckelordet `let` används för att ange bindningen för en oföränderlig variabel. Åtgärdsargument är alltid oföränderliga.

Om du behöver en variabel vars värde kan ändras, till exempel `numOnes` i exemplet, kan du deklarera variabeln med nyckelordet `mutable`. Ett värde för en föränderlig variabel kan ändras med hjälp av en `set`-instruktion.

I båda fallen härleds variabeltypen av kompileraren. Q# kräver inte någon typanteckning för variabler.

### <a name="about-using-statements-in-q"></a>Om `using`-instruktioner i Q#

`using`-instruktionen är också unik för Q#. Den används till att allokera kvantbitar som ska användas i ett kodblock. I Q# allokeras och frigörs alla kvantbitar dynamiskt, i stället för att vara fasta resurser som finns där under hela livslängden för en komplex algoritm. En `using`-instruktion allokerar en uppsättning kvantbitar vid starten och frigör dem sedan i slutet av blocket.

## <a name="create-the-host-application-code"></a>Skapa värdprogramkoden

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Öppna filen `host.py` och lägg till följande kod:

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

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

1. Ersätt innehållet i filen `Driver.cs` med följande kod:

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

### <a name="about-the-host-application-code"></a>Om värdprogramkoden

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

Python-värdprogrammet består av tre delar:

* Beräkna eventuella argument som krävs för kvantalgoritmen. I exemplet är `count` ett fast värde på 1000 och `initial` är det ursprungliga värdet för kvantbiten.
* Kör kvantalgoritmen genom att anropa metoden `simulate()` i den importerade Q#-åtgärden.
* Bearbeta resultatet för åtgärden. I det här exemplet tar `res` emot resultatet av åtgärden. Här är resultatet en tuppel med antalet nollor (`num_zeros`) och antalet ettor (`num_ones`) som har mätts av simulatorn. Vi dekonstruerar tuppeln för att få de två fälten och skriver ut resultatet.

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

C#-värdprogrammet består av fyra delar:

* Konstruera en kvantsimulator. I exemplet är `qsim` simulatorn.
* Beräkna eventuella argument som krävs för kvantalgoritmen. I exemplet är `count` ett fast värde på 1000 och `initial` är det ursprungliga värdet för kvantbiten.
* Köra kvantalgoritmen. Varje Q#-åtgärd genererar en C#-klass med samma namn. Den här klassen innehåller en `Run`-metod som **asynkront** utför åtgärden. Körningen är asynkron eftersom körningen på den faktiska maskinvaran kommer att vara asynkron. Eftersom metoden `Run` är asynkron, hämtar vi egenskapen `Result`. Den blockerar körningen tills aktiviteten har slutförts och returnerar resultatet synkront.
* Bearbeta resultatet av åtgärden. I det här exemplet tar `res` emot resultatet av åtgärden. Här är resultatet en tuppel med antalet nollor (`numZeros`) och antalet ettor (`numOnes`) som har mätts av simulatorn. Detta returneras som en ValueTuple i C#. Vi dekonstruerar tuppeln för att få de två fälten, skriver ut resultatet och väntar på en tangenttryckning.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Skapa och kör

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Kör följande kommando i terminalen:

    ```
    python host.py
    ```

    Det här kommandot kör värdprogrammet, vilket simulerar Q#-åtgärden.

Resultatet bör vara:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-codetabtabid-csharp"></a>[Kommandorad/Visual Studio Code](#tab/tabid-csharp)

1. Kör följande i terminalen:

    ```bash
    dotnet run
    ```

    Kommandot hämtar automatiskt alla nödvändiga paket, skapar programmet och kör det sedan på kommandoraden.

1. Du kan också trycka på **F1** för att öppna kommandopaletten och välja **Felsökning: Starta utan felsökning.**
Du kan uppmanas att skapa en ny ``launch.json``-fil som beskriver hur man startar programmet.
Standardvärdet ``launch.json`` fungerar bra för de flesta program.

Resultatet bör vara:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studiotabtabid-vs2019"></a>[Visual Studio](#tab/tabid-vs2019)

1. Du behöver bara trycka på `F5` för att ditt program ska börja byggas och köras!

Resultatet bör vara:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Programmet avslutas när du har tryckt på en tangent.

* * *

## <a name="prepare-superposition"></a>Förbered superposition

**Översikt** Nu ska vi titta på hur Q# uttrycker de sätt som finns för att placera kvantbitar i superposition.  Kom ihåg att tillståndet för en kvantbit kan vara i en superposition på 0 och 1.  Vi använder `Hadamard`-åtgärden för att åstadkomma detta. Om kvantbiten finns i något av de klassiska tillstånden (där en mätning alltid returnerar `Zero` eller `One`), kommer `Hadamard`- eller `H`-åtgärden att försätta kvantbiten i ett tillstånd där en mätning returnerar `Zero` 50 % av tiden och `One` 50 % av tiden.  Begreppsmässigt kan man tänka att kvantbiten är halvvägs mellan `Zero` och `One`.  När vi nu simulerar `TestBellState`-åtgärden ser vi att resultaten returnerar ungefär lika många `Zero` och `One` efter mätningen.  

Först försöker vi bara att vända kvantbiten (om den är i `Zero`-tillstånd kommer den att vändas till `One` och vice versa). Detta görs genom att köra en `X`-åtgärd innan den mäts i `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Resultatet blir omvänt (efter att du har tryckt på `F5`):

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Men allt som vi har sett hittills är klassiskt. Nu ska vi ha ett kvantresultat. Allt vi behöver göra är att ersätta `X`-åtgärden i föregående körning med en `H`- eller Hadamard-åtgärd. I stället för att vända kvantbiten hela vägen från 0 till 1, vänder vi bara den halvvägs. De ersatta raderna i `TestBellState` ser nu ut så här:

```qsharp
H(qubit);
let res = M(qubit);
```

Nu blir resultatet mer intressant:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Varje gång vi mäter ber vi om ett klassiskt värde, men kvantbiten är halvvägs mellan 0 och 1, så vi får (statistiskt sett) 0 halva tiden och 1 halva tiden. Detta kallas för __superposition__ och ger oss den första verkliga inblicken i ett kvanttillstånd.

## <a name="prepare-entanglement"></a>Förbereda sammanflätning

**Översikt:**  Nu ska vi titta på hur Q# uttrycker de sätt som finns för att sammanfläta kvantbitar.  Först försätter vi den första kvantbiten i det ursprungliga tillståndet och sedan använder vi `H`-åtgärden för att placera den i superposition.  Innan vi mäter den första kvantbiten använder vi en ny åtgärd (`CNOT`), som står för Controlled-Not.  Resultatet när vi har kört åtgärden på två kvantbitar är att vända den andra kvantbiten om den första kvantbiten är `One`.  Nu är de två kvantbitarna sammanflätade.  Vår statistik för den första kvantbiten har inte ändrats (50/50 möjlighet för `Zero` eller `One` efter mätningen), men när vi nu mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten. Vår `CNOT` har sammanflätat de två kvantbitarna, vilket innebär att det som händer med en av dem händer även för den andra. Om du skulle omvända mätningarna (den andra kvantbiten före den första), skulle samma sak inträffa. Det första måttet blir slumpmässigt och det andra blir låst med det värde som identifierades för den första mätningen.

Det första vi måste göra är att allokera två kvantbitar i stället för en i `TestBellState`:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Detta innebär att vi kan lägga till en ny åtgärd (`CNOT`) innan vi mäter (`M`) i `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Vi har lagt till en annan `Set`-åtgärd för att initiera den första kvantbiten, för att säkerställa att den alltid är i `Zero`-tillståndet när vi startar.

Vi måste också återställa den andra kvantbiten innan den frigörs.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

Den fullständiga rutinen ser nu ut så här:

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

Om vi kör detta får vi exakt samma 50/50-resultat som vi fick tidigare. Men vad vi är intresserade av är hur den andra kvantbiten reagerar på den första mätningen. Vi kommer att lägga till denna statistik med en ny version av `TestBellState`-åtgärden:

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

Det nya returvärdet (`agree`) registrerar varje gång mätningen av den första kvantbiten matchar mätningen av den andra kvantbiten. Vi måste också uppdatera värdprogrammet på lämpligt sätt:

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

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

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

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

Nu när vi kör ser vi något fantastiskt:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Som vi visade i översikten har vår statistik för den första kvantbiten inte ändrats (50/50 möjlighet för 0 eller 1), men när vi mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten eftersom de är sammanflätade.

Grattis, du har skrivit ditt första kvantprogram!

## <a name="whats-next"></a>Nästa steg

Snabbstarten för [Grovers sökning](xref:microsoft.quantum.quickstarts.search) visar hur du skapar och kör Grovers sökning, en av de mest populära kvantberäkningsalgoritmerna. Den är ett bra exempel på ett Q#-program som kan användas för att lösa verkliga problem med kvantberäkning.  

I [Kom igång med Quantum Development Kit](xref:microsoft.quantum.welcome) finns fler sätt att lära sig Q# och kvantprogrammering på.

