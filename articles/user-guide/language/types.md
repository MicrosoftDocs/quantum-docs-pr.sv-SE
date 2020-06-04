---
title: Typer i Q#
description: 'Lär dig mer om de olika typerna som används i programmeringsspråk för Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327296"
---
# <a name="types-in-q"></a>Typer i Q#

På den här sidan får du en modell av typen Q # och beskriver syntaxen för att ange och arbeta med typer.
Nästa sida, [Skriv uttryck](xref:microsoft.quantum.guide.expressions), information om hur du skapar och arbetar med uttryck av dessa typer.

Vi noterar att Q # är ett *starkt inskrivet* språk, så att en noggrann användning av dessa typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.
För att tillhandahålla starkast möjliga garantier är konverteringar mellan typer i Q # explicita med anrop till funktioner som uttrycker konverteringen. En rad olika funktioner tillhandahålls som en del av <xref:microsoft.quantum.convert> namn området.
Omsändningar till kompatibla typer av andra händer implicit. 

Q # tillhandahåller båda primitiva typer, som kan användas direkt och en mängd olika sätt att skapa nya typer från andra typer.
Vi beskriver var och en i resten av det här avsnittet.

## <a name="primitive-types"></a>Primitiva typer

Q #-språket innehåller flera *primitiva typer*, från vilka andra typer kan konstrueras:

- `Int`Typen representerar ett 64-bitars heltal, t. ex.: `2` , `107` , `-5` .
- `BigInt`Typen representerar ett signerat heltal av godtycklig storlek, t. ex., `2L` `107L` `-5L` .
   Den här typen baseras på .NET<xref:System.Numerics.BigInteger>
   bastyp.
- `Double`Typen representerar ett flyttal med dubbel precision, t. ex.: `0.0` , `-1.3` , `4e-7` .
- `Bool`Typen representerar ett booleskt värde som antingen kan vara `true` eller `false` .
- `Range`Typen representerar en sekvens med heltal, som betecknas av `start..step..stop` , där det är valfritt att ange steget. 
   Detta `start .. stop` motsvarar `start..1..stop` , och t. ex. `1..2..7` representerar sekvensen $ \{ 1, 3, 5, 7 \} $.
- `String`Typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.
  Den här typen används för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.
- `Unit`Typen är den typ som endast tillåter ett värde `()` . 
  Den här typen används för att indikera att funktionen Q # Function eller operation returnerar ingen information. 
- `Qubit`Typen representerar en Quantum-bit eller en qubit.
   `Qubit`s är ogenomskinlig för användaren. Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).
   Slutligen `Qubit` implementeras åtgärder på s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en simulering av detta).
- `Pauli`Typen representerar en av de fyra Pauli-operatörerna med en-qubit.
   Den här typen används för att beteckna bas operationen för rotationer och för att ange den som ska mätas.
   Detta är en uppräknings typ som har fyra möjliga värden: `PauliI` , `PauliX` , `PauliY` och `PauliZ` , som är konstanter av typen `Pauli` .
- `Result`Typen representerar resultatet av ett mått.
   Detta är en uppräknings typ med två möjliga värden: `One` och `Zero` , som är konstanter av typen `Result` .
   `Zero`anger att + 1-eigenvalue mättes; `One`anger-1-eigenvalue.

Konstanterna,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` och `Zero` är alla reserverade symboler i Q #.

## <a name="array-types"></a>Mat ris typer

Med en giltig Q #-typ finns `'T` en typ som representerar en matris med värden av typen `'T` .
Den här mat ris typen visas som `'T[]` till exempel `Qubit[]` eller `Int[][]` .
Till exempel är en samling av heltal som anges `Int[]` , medan en matris med `(Bool, Pauli)` värden anges `(Bool, Pauli)[][]` .

I det andra exemplet noterar du att detta representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris.
Q # ger inte stöd för rektangulära flerdimensionella matriser.

Ett mat ris värde kan skrivas i Q #-källkod med hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]` .
Typen av mat ris literal bestäms av den gemensamma bastypen för alla objekt i matrisen. Att försöka skapa en matris med element som inte har någon gemensam bastyp kommer att generera ett fel.  
Ett exempel på detta finns i [matriser med callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables) .

> [!WARNING]
> Elementen i en matris kan inte ändras efter att matrisen har skapats.
> Du kan använda uttryck för att [Uppdatera och omtilldela](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) och/eller [Kopiera och uppdatera](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) för att skapa en modifierad matris.

Du kan också skapa en matris från dess storlek med hjälp av `new` nyckelordet:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

I båda fallen kan funktionen Core `Length` användas för att hämta antalet element som ett när en matris har konstruerats `Int` .
Matriser kan skrivas med hakparenteser med hjälp av nedsänkta hakparenteser, som antingen har typ `Int` eller typ `Range` , för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.
Under skripten för matriser är noll-baserade:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tuple-typer

För noll eller flera olika typer `T0` , `T1` ,..., `Tn` kan vi *Ange* en ny tupel som `(T0, T1, ..., Tn)` .
De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))` .
Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.

Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.
Är till exempel `(3, false)` en tupel vars typ är Tuple-typen `(Int, Bool)` .
Det går att skapa matriser av tupler, tupler av matriser, tupler av under tupler osv.

Från och med Q # 0,3, `Unit` är namnet på den tomma tupelens *typ* , `()` används för det tomma tuple- *värdet*.

Tupel-instanser är oföränderliga.
Q # innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.

Tupler är ett kraftfullt koncept som används i Q # för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.
I synnerhet kan vi, om du använder tupel notation, uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.

### <a name="singleton-tuple-equivalence"></a>Jämförelse av singleton-tupel

Det går att skapa en singleton-tupel (Single-element), `('T1)` till exempel `(5)` eller `([1,2,3])` .
Q # behandlar dock en singleton-tupel som är helt likvärdig med värdet för den omslutna typen.
Det innebär att det inte finns någon skillnad mellan `5` och `(5)` , eller mellan `5` och `(((5)))` , eller mellan `(5, (6))` och `(5, 6)` .
Det är precis som giltigt för att skriva `(5)+3` till Skriv `5+3` och båda uttrycken kommer att utvärderas till `8` .

Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.
Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.
Är till exempel `(7)` ett `Int` uttryck, `([1,2,3])` är ett uttryck av typen matris för `Int` s och `((1,2))` är ett uttryck med typen `(Int, Int)` .

Det innebär särskilt att en åtgärd eller funktion vars typ av tupel eller utgående tuple har ett fält kan betraktas som ett enda argument eller returnerar ett enda värde.

Vi refererar till denna egenskap som _likhet med singleton-tupel_.


## <a name="user-defined-types"></a>Användardefinierade typer

En användardefinierad typ deklaration består av nyckelordet `newtype` , följt av namnet på den användardefinierade typen, en `=` , en giltig typ specifikation och ett avslutande semikolon.

Ett exempel:

```qsharp
newtype PairOfInts = (Int, Int);
```

Varje Q #-källfil kan deklarera ett valfritt antal användardefinierade typer.
Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.

Användardefinierade typer är distinkta även om bas typerna är identiska.
I synnerhet finns det ingen automatisk konvertering mellan värden av två användardefinierade typer, även om de underliggande typerna är identiska.

### <a name="named-vs-anonymous-items"></a>Namngivna kontra anonyma objekt

En Q #-fil kan definiera en ny namngiven typ som innehåller ett enda värde av juridisk typ.
För alla typer av tupler `T` kan vi deklarera en ny användardefinierad typ som är en undertyp till `T` `newtype` instruktionen.
I @"microsoft.quantum.math" namn rymden definieras exempelvis komplexa tal som en användardefinierad typ:

```qsharp
newtype Complex = (Double, Double);
```
Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double` .   

Förutom anonyma objekt stöder användardefinierade typer också *namngivna objekt* från och med Q # version 0,7 eller högre. Vi kan till exempel ha namngett till-objekten `Re` för det dubbla som representerar den verkliga delen av ett komplext tal och `Im` för den imaginära delen: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds. Dessutom kan inre objekt också namnges.
Typen `Nested` som definieras nedan har exempelvis en underliggande typ `(Double, (Int, String))` , varav endast objekt av typen `Int` heter och alla andra objekt är anonyma. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Namngivna objekt har fördelen att de kan nås direkt via *åtkomst operatören* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.
Till exempel på `Complex` , en kan också ha definierat 2D polär-koordinater som en användardefinierad typ:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Även om både `Complex` och båda `Polar` har en underliggande typ `(Double, Double)` , är de två typerna helt inkompatibla i Q #, vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.
På så sätt har användardefinierade typer en liknande roll som poster i F # till exempel. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Komma åt anonyma objekt med unwrap-operatorn

För att kunna komma åt anonyma objekt måste det omslutna värdet först extraheras med hjälp av postfix-operatorn `!` .
Med "unwrap"-operatorn kan `!` du extrahera värdet som finns i en användardefinierad typ.
Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Unwrap-operatorn omger ett exakt rad brytnings lager.
Flera unwrap-operatorer kan användas för att få åtkomst till ett multiplicering-figursatt värde.

Till exempel:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Du hittar mer information om unwrap-operatorn [i typ uttryck i Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Skapa värden av användardefinierade typer

Värden för en användardefinierad typ kan skapas genom att anropa motsvarande typ av konstruktor:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Precis som för matriser kopierar sådana uttryck alla objekt värden för det ursprungliga uttrycket, med undantag för de angivna namngivna objekten. För dessa värden anges de som definierats till höger i uttrycket. Andra språk konstruktioner, t. ex. [uppdaterings-och omtilldelnings instruktioner](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), som är tillgängliga för mat ris objekt, finns även för namngivna objekt i användardefinierade typer.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Användardefinierade typer kan användas var som helst av andra typer.
I synnerhet är det möjligt att definiera en matris av en användardefinierad typ och för att inkludera en användardefinierad typ som ett element av en tupel-typ.

Obs! det går inte att skapa rekursiva typ strukturer.
Det vill säga den typ som definierar en användardefinierad typ får inte vara en tuple-typ som innehåller ett element av den användardefinierade typen.
I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning typ definitioner skulle vara ogiltiga:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Åtgärds-och funktions typer

Den grundläggande typen för anrop är skriven som `('Tinput => 'Tresult)` eller `('Tinput -> 'Tresult)` , där både `'Tinput` och `'Tresult` är typer.
Dessa kallas *signaturen* för anropbar.

Alla Q # callables anses ta ett enda värde som indata och returnera ett enda värde som utdata.
Både in-och utdata-värden kan vara tupler.
Callables som inte returnerade resultat `Unit` .
Callables som inte har något inmatade tar den tomma tuppeln som inmatad.

> [!NOTE]
> Det första formuläret, med `=>` , används för åtgärder, det andra formuläret, med `->` , för functions.
> Till exempel `((Qubit, Pauli) => Result)` representerar signaturen för en möjlig mätnings åtgärd med en qubit.
*Funktions* typer anges fullständigt av signaturen.
En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)` .

*Åtgärder*---men fungerar inte---ha vissa ytterligare egenskaper som uttrycks som en del av åtgärds typen. Dessa egenskaper innehåller information om vad *functors* åtgärden stöder.
Om till exempel körning av åtgärden kan konditioneras i andra qubits-tillstånd, måste den ha stöd för `Controlled` Functor. om åtgärden har ett Inverse ska den ha stöd för `Adjoint` Functor. Functors och åtgärder beskrivs i detalj vid [drift och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions), men här diskuterar vi bara hur detta ändrar signaturen för åtgärden.

För att kunna kräva stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ måste vi lägga till en anteckning som anger motsvarande egenskaper.
En anteckning `is Ctl` (t. ex. `(Qubit => Unit is Ctl)` ) visar att åtgärden är kontrollerbar---att den körs i tillståndet för en annan qubit eller qubits. På samma sätt `is Adj` anger att åtgärden har ett överordnat objekt eller bara kan den vara "inverterad", som att använda en åtgärd och sedan dess angränsande till ett tillstånd lämnar statusen oförändrad. 

Om vi vill kräva att en åtgärd av den typen stöder både- `Adjoint` och `Controlled` Functor kan vi uttrycka detta som `(Qubit => Unit is Adj + Ctl)` . Den inbyggda Pauli-åtgärden har till exempel <xref:microsoft.quantum.intrinsic.x> typen `(Qubit => Unit is Adj + Ctl)` . 

En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.

### <a name="type-parameterized-functions-and-operations"></a>Typ-parameter funktioner och åtgärder

Typer som kan anropas kan innehålla typ parametrar.
Typ parametrar anges med en symbol som föregås av ett enkelt citat tecken. till exempel `'A` är en juridisk typ parameter.
Information om hur du definierar typ Parameters-callables finns på sidan [åtgärder och funktioner på Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .

En typ parameter kan visas mer än en gång i en enda signatur.
En funktion som till exempel tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signatur `(('A[], 'A->'A) -> 'A[])` .
På samma sätt kan en funktion som returnerar sammansättningen av två åtgärder ha signatur `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

När du anropar en typ-parameter anrops bara, måste alla argument som har samma typ parameter vara av samma typ.

Q # innehåller ingen mekanism för att begränsa de möjliga typer som kan ersättas av en typ parameter.

## <a name="next-steps"></a>Nästa steg

Nu när du har sett alla typer som utgör Q #-språket kan du [Ange uttryck i Q #](xref:microsoft.quantum.guide.expressions) för att se hur du skapar och ändrar uttryck för dessa olika typer.


