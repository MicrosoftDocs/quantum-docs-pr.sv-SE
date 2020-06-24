---
title: 'Skriv och simulera qubit-program i Q #'
description: Stegvisa anvisningar om hur du skriver och simulerar ett Quantum-program som fungerar på individuell qubit-nivå
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: e7ebdec4cd1aa201030d82759a3aa56473b26417
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275345"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Självstudie: Skriv och simulera qubit-program i Q\#

Välkommen till själv studie kursen om Quantum Development Kit om hur du skriver och simulerar ett grundläggande Quantum-program som fungerar på enskilda qubits. 

Även om Q # ursprungligen skapades som ett högnivå-programmeringsspråk för storskaliga Quantum-program, kan det vara lika enkelt att använda för att utforska den lägre nivån av Quantum-program: direkt med specifika qubits.
Flexibiliteten i Q # gör det möjligt för användare att närma sig Quantum Systems från en sådan abstraktions nivå, och i den här självstudien får vi qubits själva.
Mer specifikt tar vi en titt på den [Quantum Fourier-transformeringen](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), en subrutin som är integrerad med många större Quantum-algoritmer.

Observera att den här lågnivå visningen av Quantum information Processing ofta beskrivs i termer av "[Quantum-kretsar](xref:microsoft.quantum.concepts.circuits)", som representerar sekventiell användning av portar till specifika qubits i ett system.

Det innebär att en och flera qubit-åtgärder som vi tillämpar sekventiellt kan visas i ett "krets diagram".
I vårt fall definierar vi en Q #-åtgärd för att utföra en fullständig qubit Quantum Fourier-transformering, som har följande åter givning som krets:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Krav

* [Installera](xref:microsoft.quantum.install) Quantum Development Kit med din önskade språk-och utvecklings miljö.
* Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen


## <a name="in-this-tutorial-youll-learn-how-to"></a>I den här självstudien får du lära dig att:

> [!div class="checklist"]
> * Definiera Quantum-åtgärder i Q #
> * Anropa Q #-åtgärder direkt från kommando raden eller med hjälp av ett klassiskt värd program
> * Simulera en Quantum-åtgärd från qubit-allokering till mått utdata
> * Observera hur Quantum Systems simulerade wavefunction utvecklas under hela åtgärden

Att köra ett Quantum-program med Microsofts Quantum Development Kit består vanligt vis av två delar:
1. Själva programmet, som implementeras med hjälp av programmeringsspråket Q # Quantum, och sedan anropas för körning på en Quantum-dator eller Quantum-Simulator. Detta består av 
    - Q #-åtgärder: under rutiner som fungerar på Quantum-register och 
    - Q # functions: klassiska under rutiner som används inom Quantum-algoritmen.
2. Start punkten som används för att anropa programmet Quantum och ange den måldator som den ska köras på.
    Detta kan göras direkt från kommando raden eller via ett värd program som skrivits i ett klassiskt programmeringsspråk som python eller C#.
    Den här självstudien innehåller instruktioner för vilken metod du föredrar.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Allokera qubits och definiera Quantum-åtgärder

Den första delen av den här självstudien består av att definiera Q # `Perform3qubitQFT` -åtgärden, som utför Fourier-transformeringen på tre qubits. 

Dessutom kommer vi [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) att använda funktionen för att se hur den simulerade wavefunction av vårt tre qubit-system utvecklas över hela åtgärden.

Det första steget är att skapa ditt Q #-projekt och-fil.
Stegen för detta beror på vilken miljö du ska använda för att anropa programmet, och du hittar informationen i respektive [installations guide](xref:microsoft.quantum.install).

Vi vägleder dig genom komponenterna i filen Step-by-Step, men koden är även tillgänglig som ett fullständigt block nedan.

### <a name="namespaces-to-access-other-q-operations"></a>Namn områden för att få åtkomst till andra Q #-åtgärder
Inuti filen definierar vi först namn området `NamespaceQFT` som ska användas av kompileraren.
För att vår åtgärd ska kunna använda befintliga Q #-åtgärder öppnar vi relevanta `Microsoft.Quantum.<>` namn områden.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Definiera åtgärder med argument och returer
Nu definierar vi `Perform3qubitQFT` åtgärden:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

För tillfället tar åtgärden inga argument och returnerar inte något---i det här fallet skriver vi att den returnerar ett `Unit` objekt, som är via till `void` i C# eller en tom tupel, `Tuple[()]` i python.
Senare kommer vi att ändra den så att den returnerar en matris med mät resultat, då `Unit` ersätts punkten med `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Allokera qubits med`using`
Inom vår Q #-åtgärd allokerar vi först ett register över tre qubits med `using` instruktionen:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

Med `using` tilldelas qubits automatiskt i $ \ket {0} $-tillstånd. Vi kan verifiera detta genom att använda [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) och [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , som skriver ut en sträng och systemets aktuella tillstånd till-konsolen.

> [!NOTE]
> `Message(<string>)`-Och- `DumpMachine()` funktionerna ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) både från och [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) respektive) skrivs direkt till-konsolen. Precis som en verklig Quantum-beräkning tillåter inte Q # att vi direkt kommer åt qubit-tillstånd.
> I takt `DumpMachine` med att mål datorns aktuella tillstånd skrivs ut, kan det dock ge värdefull information om fel sökning och inlärning när det används tillsammans med fullständig tillstånds Simulator.


### <a name="applying-single-qubit-and-controlled-gates"></a>Använda en qubit och kontrollerade portar

Därefter tillämpar vi de portar som utgör själva åtgärden.
Q # innehåller redan många grundläggande Quantum-grindar som åtgärder i [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namn området och dessa är inget undantag. 

Inom en Q #-åtgärd körs de instruktioner som anropar callables i turordning.
Den första porten som ska tillämpas är därför [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) för den första qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Om du vill tillämpa en åtgärd på en viss qubit från ett register (d.v.s. en enskild `Qubit` från en matris `Qubit[]` ) använder vi standard index notation.
Det gör att du kan använda den [`H`](xref:microsoft.quantum.intrinsic.h) första qubit i vårt register för att göra `qs` formuläret:

```qsharp
            H(qs[0]);
```

Förutom att tillämpa `H` Hadamard-porten på enskilda qubits, består QFT-kretsen främst av kontrollerade [`R1`](xref:microsoft.quantum.intrinsic.r1) rotationer.
En `R1(θ, <qubit>)` åtgärd i allmänhet lämnar $ \ket {0} $-komponenten i qubit oförändrad och använder en rotation av $e ^ {i\theta} $ till $ \ket {1} $-komponenten.

#### <a name="controlled-operations"></a>Kontrollerade åtgärder

Q # gör det mycket enkelt att utvärdera körningen av en åtgärd på en eller flera qubits.
I allmänhet inleder vi bara anropet med `Controlled` och åtgärds argumenten ändras som:

 `Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .

Observera att kontrollen qubits måste anges som en matris, även om det är en enskild qubit.

Efter det `H` ser vi att nästa grind är de portar som `R1` agerar på den första qubit (och styrs av den andra/tredje):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Vi kallar dessa med

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Observera att vi använder [`PI()`](xref:microsoft.quantum.math.pi) funktionen från [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namn området för att definiera rotationen i form av pi radianer.
Dessutom delas vi upp av en `Double` (t. ex. `2.0` ) eftersom division av ett heltal `2` skulle resultera i ett typ fel. 

> [!TIP]
> `R1(π/2)`och `R1(π/4)` motsvarar `S` `T` -och-åtgärderna (även i `Microsoft.Quantum.Intrinsic` ).


Efter att ha tillämpat relevanta `H` åtgärder och kontrollerade rotationer för den andra och tredje qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

Vi behöver bara tillämpa en [`SWAP`](xref:microsoft.quantum.intrinsic.swap) grind för att slutföra kretsen:

```qsharp
            SWAP(qs[2], qs[0]);
```

Detta är nödvändigt eftersom typen av Fourier-transformeringen matar ut qubits i omvänd ordning, så att växlingarna tillåter sömlös integrering av underrutinen i större algoritmer.

Vi har därför skrivit klart qubit-åtgärderna för Quantum Fourier-transformeringen i vår Q #-åtgärd:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Vi kan dock inte anropa den en dag ännu.
Vår qubits har status $ \ket {0} $ när vi allokerade dem, och ungefär som i livet, i Q # bör vi lämna saker på samma sätt som vi hittade dem (eller bättre!).

### <a name="deallocate-qubits"></a>Frigör qubits

Vi anropar [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) igen för att se status efter åtgärden och slutligen använder du [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) qubit-registret för att återställa vår qubits till $ \ket {0} $ innan du Slutför åtgärden:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Att kräva att alla avallokerade qubits uttryckligen anges till $ \ket {0} $ är en grundläggande funktion i Q #, eftersom det gör det möjligt för andra åtgärder att identifiera sitt tillstånd exakt när de börjar använda samma qubits (en begränsade-resurs).
Detta säkerställer också att de inte är Entangled med andra qubits i systemet.
Om återställningen inte utförs i slutet av ett `using` tilldelnings block kommer ett körnings fel att genereras.

Den fullständiga Q #-filen bör nu se ut så här:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


När Q #-filen och åtgärden har slutförts är vårt Quantum-program klart att anropas och simuleras.

## <a name="execute-the-program"></a>Kör programmet

När vi har definierat vår Q #-åtgärd i en `.qs` fil måste vi nu anropa den åtgärden och observera eventuella data som returneras.
För tillfället finns det inga returnerade (kom ihåg att vår åtgärd som definierats ovan returnerar `Unit` ), men när vi senare ändrar Q #-åtgärden för att returnera en matris med mått resultat ( `Result[]` ), kommer vi att adressera detta.

Medan Q #-programmet är allmänt förekommandet i de miljöer som används för att anropa det, kan det vara självklart att göra det. Det gör du genom att följa anvisningarna i den flik som motsvarar konfigurationen: arbeta från kommando rads programmet för Q # eller använda ett värd program i python eller C#.

#### <a name="command-line"></a>[Kommandorad](#tab/tabid-cmdline)

Att köra Q #-programmet från kommando raden kräver bara en liten ändring i Q #-filen.

Lägg bara till `@EntryPoint()` på en rad före åtgärds definitionen:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Om du vill köra programmet öppnar du terminalen i mappen i projektet och anger

```dotnetcli
dotnet run
```

Vid körningen bör du se `Message` och `DumpMachine` utmatningarna nedan som skrivs ut i konsolen.


#### <a name="python"></a>[Python](#tab/tabid-python)

Skapa en python-värd fil: `host.py` .

Värd filen skapas på följande sätt: 
1. Först importerar vi `qsharp` modulen som registrerar modulens inläsare för Q #-samverkan. 
    Detta gör att Q #-namnområden (t. ex. `NamespaceQFT` vi definierat i vår Q #-fil) visas som python-moduler, där vi kan importera Q #-åtgärder.
2. Importera sedan de Q #-åtgärder som vi kommer att anropa direkt---i det här fallet `Perform3qubitQFT` .
    Vi behöver bara importera start punkten till ett Q #-program (d.v.s. _inte_ åtgärder som `H` och `R1` , som anropas av andra Q #-åtgärder men aldrig av den klassiska värden).
3. I simulera Q #-åtgärder eller-funktioner använder du formuläret `<Q#callable>.simulate(<args>)` för att köra dem på `QuantumSimulator()` mål datorn. 

> [!NOTE]
> Om vi ville anropa åtgärden på en annan dator, till exempel `ResourceEstimator()` , skulle vi bara använda `<Q#callable>.estimate_resources(<args>)` .
> I allmänhet är Q #-åtgärder oberoende till de datorer där de körs, men vissa funktioner som `DumpMachine` kan fungera annorlunda.

4. När du utför simuleringen returnerar åtgärds anropet värden som definieras i Q #-filen.
    För tillfället finns inga returnerade, men senare visas ett exempel på att tilldela och bearbeta dessa värden.
    Med resultat data i våra händer och helt klassiska kan vi göra vad vi vill med det.

Den fullständiga `host.py` filen bör vara följande:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Kör python-filen och skriv ut i konsolen. du bör se `Message` och `DumpMachine` utdata nedan. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Följ samma instruktioner som i [installations guiden](xref:microsoft.quantum.install.cs), skapa en C#-värd fil och Byt namn på den till `host.cs` .

C#-värden består av fyra delar:
1. Konstruera en kvantsimulator.
    I koden nedan är detta variabeln `qsim` .
2. Beräkna eventuella argument som krävs för kvantalgoritmen.
    Det finns inga i det här exemplet.
3. Köra kvantalgoritmen. 
    Varje Q#-åtgärd genererar en C#-klass med samma namn. 
    Den här klassen innehåller en `Run`-metod som **asynkront** utför åtgärden.
    Körningen är asynkron eftersom körningen på den faktiska maskinvaran kommer att vara asynkron. 
    Eftersom `Run` metoden är asynkron anropar vi `Wait()` metoden. Detta blockerar körningen tills aktiviteten har slutförts och returnerar resultatet synkront. 
4. Bearbeta det returnerade resultatet för åtgärden.
    För tillfället returnerar åtgärden ingenting.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Kör programmet och dina utdata bör överensstämma nedan.
Programmet avslutas när du har tryckt på en tangent.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

När den anropas i full-State Simulator `DumpMachine()` tillhandahåller dessa flera-representationer av Quantum States wavefunction. Möjliga tillstånd för ett $n $-qubit-system kan representeras av $2 ^ n $ beräknings bas tillstånd, var och en med en motsvarande komplex koefficient (helt enkelt en amplitud och en fas).
Beräknings bas staterna motsvarar alla möjliga binära strängar $n $---det vill säga alla möjliga kombinationer av qubit-tillstånd $ \ket {0} $ och $ \ket {1} $, där varje binär siffra motsvarar en enskild qubit.

Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.
Qubit `2` är "mest betydelsefull" innebär bara att i den binära representationen av bas tillstånds vektor $ \ket{i} $, motsvarar status för qubit `2` värdet längst till vänster. Till exempel $ \ket {6} = \ket {110} $ omfattar qubits `2` och `1` både i $ \ket {1} $ och qubit `0` i $ \ket {0} $.


Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{i} $ i båda formaten kartesiska och Polar.
I detalj för den första raden i vårt indatamängds tillstånd $ \ket {000} $:
* **`|0>:`** den här raden motsvarar `0` beräknings bas läget (eftersom vår initiala status efter allokering var $ \ket {000} $, vilket skulle innebära att detta är det enda läget med sannolikheten amplitud i detta läge).
* **`1.000000 +  0.000000 i`**: sannolikheten amplitud i kartesiska-format.
* **` == `**: `equal` tecknet separerar båda motsvarande representationer.
* **`********************`**: En grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta den här tillstånds vektorn. 
* **`[ 1.000000 ]`**: det numeriska värdet för storlek
* **`    ---`**: En grafisk representation av amplitudens fas.
* **`[ 0.0000 rad ]`**: det numeriska värdet för fasen (i radianer).

Både storleken och fasen visas med en grafisk representation. Representation av storlek är enkel: visar ett fält med `*` och ju högre sannolikhet, desto större är stapeln. För fasen, se [test och fel sökning: dumpa funktioner](xref:microsoft.quantum.guide.testingdebugging#dump-functions) för möjliga symbol representationer baserat på vinkel intervall.


Den utskrivna utmatningen illustrerar därför att våra programmerade portar omvandlade vår status från

$ $ \ket{\psi} \_ {initial} = \ket {000} $ $

till 

$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

Det är precis som funktionen för transformering av qubit Fourier. 

Om du är nyfiken på hur andra ingångs tillstånd påverkas, rekommenderar vi att du spelar med att använda qubit-åtgärder före transformeringen.

## <a name="adding-measurements"></a>Lägga till mått

Ett hörn av Quantum Mechanics talar tyvärr om för oss att ett verkligt Quantum-system inte kan ha en sådan `DumpMachine` funktion. I stället tvingas vi att extrahera information via mätningar, som i allmänhet inte bara kan ge oss det fullständiga Quantum-läget, men kan också drastiskt ändra själva systemet.
Det finns många olika typer av Quantum-mätningar, men vi fokuserar på de mest grundläggande: projekt måtten för enskilda qubits.
Vid mätning i en specifik grund (t. ex. beräknings basen $ \{ \ket {0} , \ket {1} \} $), projiceras qubit-statusen på det villkor som har mätts---därför att alla överpositioner mellan de två anges.

För att implementera mätningar i ett Q #-program, använder vi `M` åtgärden (från `Microsoft.Quantum.Intrinsic` ) som returnerar en `Result` typ.

Först ändrar vi vår `Perform3QubitQFT` åtgärd för att returnera en matris med mått resultat, `Result[]` i stället för `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Definiera och initiera `Result[]` matris

Innan du ens tilldelar qubits (t. ex. före `using` uttrycket), deklarerar vi och binder denna längd-3-matris (en `Result` för varje qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

`mutable`Nyckelordet preaktiv `resultArray` tillåter att variabeln binds senare i kod---till exempel när du lägger till våra mått resultat.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Utför mätningar i en `for` slinga och Lägg till resultat i matrisen

Infoga följande kod efter Fourier Transform-åtgärder i `using` blocket:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funktionen som anropas i en matris (t. ex. vår matris av qubits `qs` ) returnerar ett intervall över indexets index. Här använder vi den i vår `for` slinga för att sekventiellt mäta varje qubit med hjälp av `M(qs[i])` instruktionen.
Varje uppmätt `Result` typ (antingen `Zero` eller `One` ) läggs sedan till i motsvarande index position i `resultArray` med en Update-och-Reassign-instruktion.

> [!NOTE]
> Syntaxen för den här instruktionen är unik för Q #, men motsvarar den liknande variabel omtilldelningen som `resultArray[i] <- M(qs[i])` visas på andra språk, till exempel F # och R.

Nyckelordet `set` används alltid för att omtilldela variabler som binds med `mutable` .

#### <a name="return-resultarray"></a>Returrelaterade`resultArray`

Med alla tre qubits som mäts och resultaten som har lagts till i `resultArray` , är det säkert att återställa och frigöra qubits som tidigare.
När `using` blockets Stäng visas infogar du

```qsharp
        return resultArray;
```
för att slutligen returnera utdata från vår åtgärd. 

### <a name="understanding-the-effects-of-measurement"></a>Förstå effekterna av mått

Nu ska vi ändra placeringen av våra `DumpMachine` funktioner för att mata ut tillstånd före och efter mätningarna.
Den slutgiltiga åtgärds koden bör se ut så här: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Om du arbetar från kommando raden skrivs den returnerade matrisen bara ut direkt till-konsolen i slutet av körningen.
Annars uppdaterar du värd programmet för att bearbeta den returnerade matrisen.

#### <a name="command-line"></a>[Kommandorad](#tab/tabid-cmdline)

Om du vill ha mer förståelse för den returnerade matrisen som ska skrivas ut i-konsolen kan vi lägga till en annan `Message` i Q #-filen precis innan `return` instruktionen:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Kör projektet och dina utdata bör se ut ungefär så här:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Uppdatera python-programmet till följande:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Kör filen och dina utdata bör se ut ungefär så här:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Nu när vår åtgärd returnerar ett resultat ersätter du metod anropet `Wait()` med att hämta `Result` egenskapen. Detta utför fortfarande samma Synchronicity som beskrivs ovan och vi kan binda det här värdet direkt till variabeln `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Kör projektet och dina utdata bör se ut ungefär så här:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

De här utdata illustrerar några olika saker:
1. Om du jämför det returnerade resultatet till för mätningen `DumpMachine` illustreras det tydligt _inte_ efter QFT överpositions tillstånd.
    En mätning returnerar bara ett enda bas tillstånd, med en sannolikhet som bestäms av amplituden för det aktuella läget i systemets wavefunction.
2. Från och med efter mätningen `DumpMachine` ser vi att måttet _ändrar_ själva tillståndet och projicerar det från den ursprungliga överplaceringen för att få till gång till det enskilda tillstånd som motsvarar det uppmätta värdet.

Om vi skulle upprepa den här åtgärden flera gånger skulle vi se resultat statistiken som börjar illustrera den lika viktade superpositionen för det QFT tillstånd som ger upphov till ett slumpmässigt resultat för varje bild.
_Men_förutom att det är ineffektivt och fortfarande är perfekt kan detta dock bara återge de relativa amplituderna i bas staterna, inte de relativa faserna mellan dem.
Den senare är inte ett problem i det här exemplet, men vi skulle se att relativa faser visas om du har fått en mer komplex inQFTare än $ \ket {000} $.

#### <a name="partial-measurements"></a>Partiella mått 
Om du vill utforska hur man mäter att endast vissa qubits av registret kan påverka systemets tillstånd kan du försöka lägga till följande i `for` slingan efter mätnings linjen:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Observera att `IntAsString` du måste lägga till funktionen för att få åtkomst till funktionen 
```qsharp
    open Microsoft.Quantum.Convert;
```
med resten av namespace- `open` uttrycken.

I resultatet visas den gradvisa projektionen i del utrymmen som varje qubit mäts.


## <a name="use-the-q-libraries"></a>Använd Q #-bibliotek
Som vi nämnde i introduktionen är det mycket av Q #-kraften i det faktum att det gör att du kan ta itu med att hantera enskilda qubits.
Om du vill utveckla fullständiga, tillämpliga Quantum-program, och oroa dig för om en `H` åtgärd går före eller efter en viss rotation, skulle det bara gå långsamt. 

Q #-biblioteken innehåller [QFT](xref:microsoft.quantum.canon.qft) -åtgärden, som du bara kan ta och använda för valfritt antal qubits.
För att ge det ett försök definierar du en ny åtgärd i din Q #-fil som har samma innehåll `Perform3QubitQFT` , men med allt från den första `H` till den `SWAP` ersatt av två enkla rader:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
Den första raden skapar helt enkelt ett [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) uttryck för den allokerade matrisen qubits, `qs` vilket är vad [QFT](xref:microsoft.quantum.canon.qft) -åtgärden tar som ett argument.
Detta motsvarar index ordningen för qubits i registret.

Om du vill ha åtkomst till dessa åtgärder lägger du till `open` instruktioner för deras respektive namnrum i början av Q #-filen:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Nu ska du justera värd programmet för att anropa namnet på din nya åtgärd (t. ex. `PerformIntrinsicQFT` ) och ge den ett försök.

Om du vill se den verkliga fördelen med att använda Q # Library-åtgärder ändrar du antalet qubits till något annat än `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Du kan därför använda rätt QFT för ett angivet antal qubits, utan att behöva oroa dig för nya `H` åtgärder och rotationer på varje qubit.

Observera att Quantum simulatorn tar exponentiellt mer tid att köra när du ökar antalet qubits---exakt varför vi ser fram emot att bli verkligt Quantum-maskinvara!













