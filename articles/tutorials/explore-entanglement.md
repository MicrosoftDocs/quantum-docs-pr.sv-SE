---
title: Utforska sammanflätning med Q#
description: Lär dig hur man skriver ett kvantprogram i Q#. Utveckla ett Bell-tillståndsprogram med Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415430"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Självstudier: Utforska sammanflätning med Q\#

I den här självstudien visar vi hur du skriver ett Q#-program som ändrar och mäter kvantbitar samt visar effekterna av superposition och sammanflätning.

Du kommer att skriva ett program med namnet Bell som visar kvantsammanflätning.
Namnet Bell syftar på Bell-tillstånd, vilket är specifika kvanttillstånd för två kvantbitar som används för att visa de enklaste exemplen på superposition och kvantsammanflätning.

## <a name="pre-requisites"></a>Förutsättningar

Om du är redo att börja koda följer du nedanstående steg innan du fortsätter: 

* [Installera](xref:microsoft.quantum.install) Quantum Development Kit med din önskade språk-och utvecklings miljö.
* Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen

Du kan också följa med i beräkningen utan att installera QDK, granska översikterna för Q #-programmeringsspråket och de första koncepten med Quantum Computing.

## <a name="in-this-tutorial-youll-learn-how-to"></a>I den här självstudien får du lära dig att:

> [!div class="checklist"]
> * Skapa och kombinera åtgärder i Q\#
> * Skapa åtgärder för att placera qubits i superposition, entangle och mät dem.
> * Demonstrera Quantum entanglement med ett Q #-program som körs i en simulator. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Demonstrera qubit-beteende med QDK

Medan klassiska bitar innehåller ett enda binärt värde, 0 eller 1, kan tillståndet för en [kvantbit](xref:microsoft.quantum.glossary#qubit) vara i en **superposition** med 0 och 1.  En qubit kan till exempel betraktas som en riktning i ett abstrakt utrymme (kallas även Vector).  Ett qubit-tillstånd kan vara i alla möjliga riktningar. De två **klassiska tillstånden** är två riktningar. De motsvarar en chans på 100 % att mäta 0 och en chans på 100 % att mäta 1.

Mätningen genererar ett binärt resultat och ändrar kvantbitens tillstånd.
Måttet genererar ett binärt värde, antingen 0 eller 1.  Kvantbiten går från att vara i superposition (vilken riktning som helst) till ett av de klassiska tillstånden.  När du därefter upprepar samma mätning utan några andra åtgärder får du samma binära resultat.  

Flera kvantbitar kan vara [**sammanflätade**](xref:microsoft.quantum.glossary#entanglement).  När vi mäter en sammanflätad kvantbit får vi även veta de andra kvantbitarnas tillstånd.

Nu är vi redo att demonstrera hur Q# uttrycker detta beteende.  Du börjar med det enklaste programmet och skapar det för att visa en kvantsuperposition och kvantsammanflätning.

## <a name="creating-a-q-project"></a>Skapa ett Q #-projekt

Det första vi behöver göra är att skapa ett nytt Q #-projekt. I den här självstudien kommer vi att använda miljön baserat på [kommando rads program med vs Code](xref:microsoft.quantum.install.standalone).

Så här skapar du ett nytt projekt i VS Code: 

1. Klicka på **Visa**  ->  **kommando palett** och välj **Q #: skapa nytt projekt**.
2. Klicka på **fristående konsol program**.
3. Navigera till platsen där du vill spara projektet och klicka på **skapa projekt**.
4. När projektet har skapats klickar du på **Öppna nytt projekt...** i det nedre högra hörnet.

I det här fallet kallas vi för projektet `Bell` . Detta genererar två filer: `Bell.csproj` , projekt filen och `Program.qs` en mall för ett Q #-program som vi ska använda för att skriva vårt program. Innehållet i `Program.qs` ska vara:

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

## <a name="write-the-q-application"></a>Skriv Q- \# programmet
 
Vårt mål är att förbereda två kvantbitar i ett särskilt kvanttillstånd, demonstrera hur du använder kvantbitar med Q# för att ändra deras tillstånd, samt demonstrera effekterna av superposition och sammanflätning. Vi bygger upp den här delen av en del för att presentera qubit-tillstånd,-åtgärder och-mått.

### <a name="initialize-qubit-using-measurement"></a>Initiera qubit med hjälp av mått

I den första koden nedan visar vi dig hur man arbetar med kvantbitar i Q#.  Vi introducerar två åtgärder [`M`](xref:microsoft.quantum.intrinsic.m) och [`X`](xref:microsoft.quantum.intrinsic.x) som transformerar statusen för en qubit. I det här kodfragmentet definieras åtgärden `SetQubitState` som använder en parameter som kvantbit och en annan parameter, `desired`, som representerar det tillstånd som vi vill att kvantbiten ska ha.  Åtgärden `SetQubitState` utför en mätning på kvantbiten med åtgärden `M`.  I Q # returnerar en qubit-mätning alltid antingen `Zero` eller `One` .  Om mätningen returnerar ett värde som inte är lika med det önskade värdet `SetQubitState` "vänder" qubit; som är, körs en `X` åtgärd som ändrar qubit-tillstånd till ett nytt tillstånd där sannolikheten för en mätning returneras `Zero` och `One` återförs. På så sätt `SetQubitState` placeras alltid mål qubit i önskat tillstånd.

Ersätt innehållet i `Program.qs` med följande kod:


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

Den här åtgärden kan nu anropas för att försätta en kvantbit i ett klassiskt tillstånd som antingen returnerar `Zero` 100 % av tiden eller `One` 100 % av tiden.
`Zero` och `One` är konstanter som representerar de enda två möjliga resultaten från en kvantbitsmätning.

Åtgärden `SetQubitState` mäter kvantbiten. Om kvantbiten är i det tillstånd som vi vill ha, lämnar `SetQubitState` den oförändrad. Annars ändrar vi kvantbitens tillstånd till önskat tillstånd genom att köra åtgärden `X`.

#### <a name="about-q-operations"></a>Om Q#-åtgärder

En Q#-åtgärd är en kvantsubrutin. Det vill säga att det är en rutin som kan anropas och som innehåller anrop till andra Quantum-åtgärder.

Argumenten i en åtgärd anges som en tuppel inom parentes.

Returtypen för åtgärden anges efter ett kolon. I det här fallet saknar `SetQubitState`-åtgärden en retur, så den markeras som en retur för `Unit`. Detta är Q#-motsvarigheten till `unit` i F#, vilket är ungefär detsamma som `void` i C# och en tom tuppel (`Tuple[()]`) i Python.

Du använde två kvantåtgärder i din första Q#-åtgärd:

* [`M`](xref:microsoft.quantum.intrinsic.m)Åtgärden, som mäter status för qubit
* [`X`](xref:microsoft.quantum.intrinsic.x)Åtgärden, som vänder sig till status för en qubit

En kvantåtgärd omvandlar tillståndet för en kvantbit. Ibland pratar man om kvantgrindar i stället för åtgärder, vilket motsvarar klassiska logiska grindar. Detta kommer från när man började använda kvantberäkning och algoritmerna bara var en teoretisk konstruktion som visualiserades som diagram, liknande kretsdiagram i klassisk databehandling.

### <a name="counting-measurement-outcomes"></a>Beräkning av mått resultat

En `TestBellState`-åtgärd läggs till för att demonstrera resultatet av åtgärden `SetQubitState`. Den här åtgärden tar `Zero` eller `One` som indata och anropar `SetQubitState`-åtgärden ett visst antal gånger med indatan. Därefter räknas det antal gånger som `Zero` returnerades från kvantbitsmätningen och antalet gånger som `One` returnerades. I den här första simuleringen av `TestBellState`-åtgärden förväntar vi oss givetvis att utdatan ska visa att alla mätningar av kvantbitsuppsättningen med `Zero` som parameterindata ska returnera `Zero`, och att alla mätningar av en kvantbitsuppsättning med `One` som parameterindata ska returnera `One`. Vidare kommer vi att lägga till kod till `TestBellState` för att demonstrera överplacering och entanglement.

Lägg till följande åtgärd i `Bell.qs`-filen (inuti namnområdet) efter att `SetQubitState`-åtgärden har slutförts:

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
Observera att vi har lagt till en rad innan `return` du skriver ut ett för klar ande meddelande i-konsolen med funktionen ( `Message` ) [Microsoft. Quantum. inneboende. Message]

Åtgärden (`TestBellState`) kommer att upprepas för `count` iterationer, ange ett angivet `initial`-värde för en kvantbit och sedan mäta (`M`) resultatet. Den samlar in statistik om hur många nollor och ettor som vi har mätt och returnerar dem till anroparen. Den utför även en annan åtgärd som krävs. Den återställer kvantbiten till ett känt tillstånd (`Zero`) innan den returnerar, så att andra kan allokera kvantbiten i ett känt tillstånd. Detta krävs av `using`-instruktionen.

#### <a name="about-variables-in-q"></a>Om variabler i Q\#

Som standard är variablerna i Q# oföränderliga. Värdet kan inte ändras efter att de har bundits. Nyckelordet `let` används för att ange bindningen för en oföränderlig variabel. Åtgärdsargument är alltid oföränderliga.

Om du behöver en variabel vars värde kan ändras, till exempel `numOnes` i exemplet, kan du deklarera variabeln med nyckelordet `mutable`. Ett värde för en föränderlig variabel kan ändras med hjälp av en `setQubitState`-instruktion.

I båda fallen härleds variabeltypen av kompileraren. Q# kräver inte någon typanteckning för variabler.

#### <a name="about-using-statements-in-q"></a>Om `using` instruktioner i Q\#

`using`-instruktionen är också unik för Q#. Den används till att allokera kvantbitar som ska användas i ett kodblock. I Q# allokeras och frigörs alla kvantbitar dynamiskt, i stället för att vara fasta resurser som finns där under hela livslängden för en komplex algoritm. En `using`-instruktion allokerar en uppsättning kvantbitar vid starten och frigör dem sedan i slutet av blocket.

## <a name="execute-the-code-from-the-command-line"></a>Kör koden från kommando raden

För att kunna köra koden måste vi ange vilken kompilator *som* kan anropas för att köras när vi anger `dotnet run` kommandot. Detta görs med en enkel ändring i Q #-filen genom att lägga till en rad med `@EntryPoint()` direkt föregående anrops funktion: `TestBellState` åtgärden i det här fallet. Den fullständiga koden ska vara:

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

För att köra programmet måste vi ange `count` och `initial` argument från kommando raden. Vi väljer till exempel `count = 1000` och `initial = One` . Ange följande kommando:

```dotnetcli
dotnet run --count 1000 --initial One
```

Och du bör Observera följande utdata:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Om du försöker med `initial = Zero` bör du följa:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Förbered superposition

Nu ska vi titta på hur Q # uttrycker sätt att placera qubits i superposition.  Kom ihåg att tillståndet för en kvantbit kan vara i en superposition på 0 och 1.  Vi använder `Hadamard`-åtgärden för att åstadkomma detta. Om kvantbiten finns i något av de klassiska tillstånden (där en mätning alltid returnerar `Zero` eller `One`), kommer `Hadamard`- eller `H`-åtgärden att försätta kvantbiten i ett tillstånd där en mätning returnerar `Zero` 50 % av tiden och `One` 50 % av tiden.  Begreppsmässigt kan man tänka att kvantbiten är halvvägs mellan `Zero` och `One`.  När vi nu simulerar `TestBellState`-åtgärden ser vi att resultaten returnerar ungefär lika många `Zero` och `One` efter mätningen.  

### <a name="x-flips-qubit-state"></a>`X`vänder qubit-tillstånd

Först försöker vi bara att vända kvantbiten (om den är i `Zero`-tillstånd kommer den att vändas till `One` och vice versa). Detta görs genom att köra en `X`-åtgärd innan den mäts i `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Nu återförs resultatet:

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

Nu ska vi utforska Quantum-egenskaperna för qubits.

### <a name="h-prepares-superposition"></a>`H`förbereder överplacering

Allt vi behöver göra är att ersätta `X`-åtgärden i föregående körning med en `H`- eller Hadamard-åtgärd. I stället för att vända kvantbiten hela vägen från 0 till 1, vänder vi bara den halvvägs. De ersatta raderna i `TestBellState` ser nu ut så här:

```qsharp
H(qubit);
let res = M(qubit);
```

Nu blir resultatet mer intressant:

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

Varje gång vi mäter ber vi om ett klassiskt värde, men kvantbiten är halvvägs mellan 0 och 1, så vi får (statistiskt sett) 0 halva tiden och 1 halva tiden.
Detta kallas för **superposition** och ger oss den första verkliga inblicken i ett kvanttillstånd.

## <a name="prepare-entanglement"></a>Förbereda sammanflätning

Nu ska vi titta på hur Q# uttrycker de sätt som finns för att sammanfläta kvantbitar.
Först försätter vi den första kvantbiten i det ursprungliga tillståndet och sedan använder vi `H`-åtgärden för att placera den i superposition.  Innan vi mäter den första qubit använder vi en ny åtgärd ( `CNOT` ), som står för kontrollerad – inte.  Resultatet när vi har kört åtgärden på två kvantbitar är att vända den andra kvantbiten om den första kvantbiten är `One`.  Nu är de två kvantbitarna sammanflätade.  Vår statistik för den första kvantbiten har inte ändrats (50/50 möjlighet för `Zero` eller `One` efter mätningen), men när vi nu mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten. Vår `CNOT` har sammanflätat de två kvantbitarna, vilket innebär att det som händer med en av dem händer även för den andra. Om du skulle omvända mätningarna (den andra kvantbiten före den första), skulle samma sak inträffa. Det första måttet blir slumpmässigt och det andra blir låst med det värde som identifierades för den första mätningen.

Det första vi behöver göra är att allokera två qubits i stället för en i `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Detta innebär att vi kan lägga till en ny åtgärd (`CNOT`) innan vi mäter (`M`) i `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Vi har lagt till en annan `SetQubitState`-åtgärd för att initiera den första kvantbiten, för att säkerställa att den alltid är i `Zero`-tillståndet när vi startar.

Vi måste också återställa den andra kvantbiten innan den frigörs.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

Den fullständiga rutinen ser nu ut så här:

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

Om vi kör detta får vi exakt samma 50/50-resultat som vi fick tidigare. Men vad vi är intresserade av är hur den andra kvantbiten reagerar på den första mätningen. Vi kommer att lägga till denna statistik med en ny version av `TestBellState`-åtgärden:

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

Det nya returvärdet (`agree`) registrerar varje gång mätningen av den första kvantbiten matchar mätningen av den andra kvantbiten.

Kör koden som vi erhåller:

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

Som vi visade i översikten har vår statistik för den första kvantbiten inte ändrats (50/50 möjlighet för 0 eller 1), men när vi mäter den andra kvantbiten är det __alltid__ samma resultat som för den första kvantbiten eftersom de är sammanflätade.

## <a name="next-steps"></a>Nästa steg

Självstudien [Grovers sökning](xref:microsoft.quantum.quickstarts.search) visar hur du skapar och kör Grovers sökning, en av de mest populära kvantberäkningsalgoritmerna. Den är ett bra exempel på ett Q#-program som kan användas för att lösa verkliga problem med hjälp av kvantberäkning.  

I [Kom igång med Quantum Development Kit](xref:microsoft.quantum.welcome) finns fler sätt att lära sig Q# och kvantprogrammering på.