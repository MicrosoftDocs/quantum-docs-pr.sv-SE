---
title: Typer i Q#
description: Lär dig mer om de olika typerna som används i Q# programmeringsspråket.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691617"
---
# <a name="types-in-no-locq"></a>Typer i Q#

I den här artikeln beskrivs Q# typ modellen och syntaxen för att ange och arbeta med typer. Mer information om hur du skapar och arbetar med uttryck av dessa typer finns i [typ uttryck](xref:microsoft.quantum.guide.expressions).

Vi noterar att det Q# är ett *starkt inskrivet* språk, så att en noggrann användning av de här typerna kan hjälpa kompileraren att tillhandahålla starka garantier om Q# program vid kompilering.
För att ge de starkaste garantier som är möjliga Q# måste konverteringen mellan olika typer vara explicit med anrop till funktioner som uttrycker konverteringen. 
Q# innehåller en rad olika funktioner som en del av <xref:Microsoft.Quantum.Convert> namn området.
Omsändningar till kompatibla typer, å andra sidan, sker implicit. 

Q# tillhandahåller båda primitiva typer, som används direkt och en mängd olika sätt att skapa nya typer av från andra typer.
Vi beskriver var och en i resten av den här artikeln.

## <a name="primitive-types"></a>Primitiva typer

Q#Språket innehåller följande *primitiva typer* , som du kan använda direkt i Q# program. Du kan också använda dessa primitiva typer för att skapa nya typer.

- `Int`Typen representerar ett 64-bitars heltal, till exempel,, `2` `107` `-5` .
- `BigInt`Typen representerar ett signerat heltal av godtycklig storlek, till exempel, `2L` , `107L` `-5L` .
   Den här typen baseras på .NET <xref:System.Numerics.BigInteger>
   bastyp.

- `Double`Typen representerar ett flyttal med dubbel precision, till exempel,, `0.0` `-1.3` `4e-7` .
- `Bool`Typen representerar ett booleskt värde för antingen `true` eller `false` .
- `Range`Typen representerar en sekvens med heltal, som betecknas av `start..step..stop` , där det är valfritt att ange steget. 
   `start .. stop`Motsvarar exempelvis `start..1..stop` , och `1..2..7` representerar sekvensen $ \{ 1, 3, 5, 7 \} $.
- `String`Typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.
  Använd `string` typen för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.
- `Unit`Typen kan bara ha ett värde, `()` . 
  Använd den här typen för att indikera att en Q# funktion eller åtgärd returnerar ingen information. 
- `Qubit`Typen representerar en Quantum-bit eller en qubit.
   `Qubit`s är ogenomskinlig för användaren. Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).
   Slutligen implementerar du åtgärder på `Qubit` s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en Quantum-Simulator).
- `Pauli`Typen representerar en av de fyra Pauli-operatörerna med en-qubit.
   Använd den här typen för att beteckna bas operationen för rotationer och för att ange den som ska mätas.
   Det är en uppräknings typ som har fyra möjliga värden: `PauliI` , `PauliX` , `PauliY` och `PauliZ` , som är konstanter av typen `Pauli` .
- `Result`Typen representerar resultatet av ett mått.
   Det är en uppräknad typ med två möjliga värden: `One` och `Zero` , som är konstanter av typen `Result` .
   `Zero` anger att + 1-eigenvalue mättes; `One` anger att-1-eigenvalue mättes.

Konstanterna,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` och `Zero` är alla reserverade symboler i Q# .

## <a name="array-types"></a>Mat ris typer

* För en giltig Q# typ finns en typ som representerar en matris med värden av den typen.
    Till exempel `Qubit[]` och `(Bool, Pauli)[]` representerar matriser med `Qubit` värden och tuple- `(Bool, Pauli)` värden.

* En matris med matriser är också giltig. Om du expanderar i föregående exempel visas en matris med `(Bool, Pauli)` matriser `(Bool, Pauli)[][]` .

> [!NOTE] 
> Det här exemplet `(Bool, Pauli)[][]` representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris. Q# stöder inte rektangulära flerdimensionella matriser.

* Ett mat ris värde kan skrivas i Q# käll koden med hjälp av hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]` .
Den gemensamma bastypen för alla objekt i matrisen bestämmer typen för en mat ris sträng. Därför genererar en matris med element som inte har någon common-bastyp ett fel.  
Ett exempel finns i [matriser med callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > När du har skapat en matris kan du inte ändra elementen i en matris.
    > Om du vill skapa en modifierad matris använder du instruktioner för att [Uppdatera och omtilldela](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) , eller [Kopiera och uppdatera uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Du kan också skapa en matris från dess storlek med hjälp av `new` nyckelordet:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Använd funktionen Core `Length` för att hämta antalet element från en matris som en `Int` .
* Matriser kan vara nedsänkta för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.
Nedsänkta matriser är noll-baserade och måste vara av typ `Int` eller typ `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Tuple-typer

Tupler är ett kraftfullt koncept som används i Q# för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.
I synnerhet kan du använda tupel-notation för att uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.

* För noll eller flera olika typer `T0` , `T1` ,..., `Tn` kan du  *Ange* en ny tupel som `(T0, T1, ..., Tn)` .
De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))` .
Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.

* Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.
Är till exempel `(3, false)` en tupel vars typ är Tuple-typen `(Int, Bool)` .
Det är möjligt att skapa matriser av tupler, tupler av matriser, tupler av under tupler och så vidare.

* Från och med Q# 0,3, `Unit` är namnet på den tomma tuplens *typ* , `()` används för *värdet* för den tomma tuppeln.

* Tupel-instanser är oföränderliga.
Q# innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.



### <a name="singleton-tuple-equivalence"></a>Jämförelse av singleton-tupel

Det går att skapa en singleton-tupel (Single-element) `('T1)` , till exempel `(5)` eller `([1,2,3])` .
Behandlar dock Q# en singleton-tupel som motsvarar ett värde för den omslutna typen.
Det innebär att det inte finns någon skillnad mellan `5` och `(5)` , eller mellan `5` och `(((5)))` , eller mellan `(5, (6))` och `(5, 6)` .
Det är bara giltigt att skriva `(5)+3` som det är att skriva `5+3` . båda uttrycken utvärderas till `8` .

Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.
Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.
Till exempel `(7)` är ett uttryck av typen `Int` , `([1,2,3])` är ett uttryck av typen `Int[]` och `((1,2))` är ett uttryck av typen `(Int, Int)` .

Det innebär framför allt att du kan visa en åtgärd eller funktion vars typ av tupel eller utgående tuple-typ har ett fält som ett enda argument eller returnerar ett enda värde.

Vi refererar till denna egenskap som _likhet med singleton-tupel_ .


## <a name="user-defined-types"></a>User-Defined typer

En användardefinierad typ deklaration består av nyckelordet `newtype` , följt av namnet på den användardefinierade typen, en `=` , en giltig typ specifikation och ett avslutande semikolon.

Exempel:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Varje Q# källfil kan deklarera ett valfritt antal användardefinierade typer.
* Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.
* Användardefinierade typer är distinkta, även om bas typerna är identiska.
I synnerhet finns det ingen automatisk konvertering mellan värdena för två användardefinierade typer, även om de underliggande typerna är identiska.

### <a name="named-vs-anonymous-items"></a>Namngivna kontra anonyma objekt

En Q# fil kan definiera en ny namngiven typ som innehåller ett enda värde av vilken juridisk typ som helst.
För vilken typ `T` av tupel som helst kan du deklarera en ny användardefinierad typ som är en undertyp till `T` `newtype` instruktionen.
I @"microsoft.quantum.math" namn rymden definieras exempelvis komplexa tal som en användardefinierad typ:

```qsharp
newtype Complex = (Double, Double);
```
Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double` .   

Förutom anonyma objekt stöder användardefinierade typer även *namngivna objekt* från Q# och med version 0,7 eller högre. Du kan till exempel namnge objekten till `Real` för det dubbla som representerar den verkliga delen av ett komplext tal och `Imag` för den imaginära delen: 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds. Dessutom kan inre objekt också namnges.
Typen `Nested` , som definieras nedan, till exempel har en underliggande typ `(Double, (Int, String))` , varav endast objekt av typen `Int` heter, och alla andra objekt är anonyma. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Namngivna objekt har fördelen att de kan nås direkt via *åtkomst operatören* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.
Till exempel på `Complex` , en kan också ha definierat en polär koordinat-represenation som en användardefinierad typ:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Även om både `Complex` och `ComplexPolar` båda har en underliggande typ `(Double, Double)` , är de två typerna helt inkompatibla i Q# , vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Komma åt anonyma objekt med unwrap-operatorn

För att komma åt anonyma objekt, extrahera först det omslutna värdet med hjälp av postfix-operatorn `!` .
Med operatorn "unwrap" `!` kan du extrahera värdet som finns i en användardefinierad typ.
Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

En enda unwrap-operator avbryter ett rad brytnings lager. Använd flera unwrap-operatorer för att få åtkomst till ett multiplicerat rad värde.

Exempel:

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

Mer information om unwrap-operatorn finns [i text uttryck i Q# ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Skapa värden av användardefinierade typer

Skapa värden för en användardefinierad typ genom att anropa motsvarande typ-konstruktor:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Precis som med matriser kopierar och uppdaterar uttryck alla objekt värden för det ursprungliga uttrycket, förutom de angivna namngivna objekten. För dessa undantag är värdena för dessa objekt de värden som definieras på höger sida av uttrycket. Andra språk konstruktioner som är tillgängliga för mat ris objekt, till exempel [Update-och-Reassign-instruktioner](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), finns för namngivna objekt i användardefinierade typer.

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

* Du kan använda användardefinierade typer överallt där du använder andra typer av typer.
I synnerhet är det möjligt att definiera en matris av en användardefinierad typ och för att inkludera en användardefinierad typ som ett element av en tupel-typ.

* Det går inte att skapa rekursiva typ strukturer.
Det vill säga den typ som definierar en användardefinierad typ kan inte vara en tupel som innehåller ett element av den användardefinierade typen.
I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning av typ definitioner är ogiltiga:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Åtgärds-och funktions typer

Utifrån typerna `'Tinput` och `'Tresult` :

* `('Tinput => 'Tresult)` är den grundläggande typen för alla *åtgärder* , till exempel `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` är den grundläggande typen för alla *funktioner* , till exempel `(Int -> Int)` . 

Dessa kallas *signaturen* för anropbar.

* Alla Q# callables tar ett enda värde som indata och returnerar ett enda värde som utdata.
* Du kan använda tupler för både in-och utdata-värden.
* Callables som inte har något resultat returneras `Unit` .
* Callables som inte har något inmatade tar den tomma tuppeln som inmatad.

### <a name="functors"></a>Functors

*Funktions* typer anges fullständigt av signaturen. En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)` . 

*Åtgärder* har vissa ytterligare egenskaper som uttrycks som en del av åtgärds typen. Dessa egenskaper innehåller information om vilka *functors* som stöds av åtgärden.
Om till exempel körningen av åtgärden förlitar sig på andra qubits-tillstånd, måste den ha stöd för `Controlled` Functor. om åtgärden har en invertering, ska den ha stöd för `Adjoint` Functor.

> [!NOTE]
> Den här artikeln beskriver endast hur functors ändrar signaturen för åtgärden. Mer information om functors och åtgärder finns [i åtgärder och funktioner i Q# ](xref:microsoft.quantum.guide.operationsfunctions). 

Om du behöver stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ måste du lägga till en anteckning som anger motsvarande egenskaper.
Anteckningen `is Ctl` (till exempel `(Qubit => Unit is Ctl)` ) visar att åtgärden är kontrollerbar. Det innebär att dess körning förlitar sig på statusen för en annan qubit eller qubits. På samma sätt betyder anteckningen `is Adj` att åtgärden har ett överordnat objekt, det vill säga att den kan vara "inverterad", så att en åtgärd som sedan är i det angränsande till ett tillstånd lämnar statusen oförändrad. 

Om du vill kräva att en åtgärd av den typen stöder både- `Adjoint` och `Controlled` Functor kan du uttrycka detta som `(Qubit => Unit is Adj + Ctl)` . Den inbyggda Pauli-åtgärden har till exempel <xref:Microsoft.Quantum.Intrinsic.X> typen `(Qubit => Unit is Adj + Ctl)` . 

En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.

### <a name="type-parameterized-functions-and-operations"></a>Type-Parameterized funktioner och åtgärder

Typer som kan anropas kan innehålla *typ parametrar* .
Använd en symbol som föregås av ett enkelt citat tecken för att indikera en typ parameter. till exempel `'A` är en juridisk typ parameter.
Mer information och information om hur du definierar callables för typ parametrar finns [i åtgärder och funktioner i Q# ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

En typ parameter kan visas mer än en gång i en enda signatur.
Till exempel en funktion som tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signaturen `(('A[], 'A->'A) -> 'A[])` .
På samma sätt har en funktion som returnerar kompositionen av två åtgärder signaturen `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

När du anropar en typ-parameter anrops bara måste alla argument som har samma typ parameter vara av samma typ.

Q# innehåller ingen mekanism för att begränsa de möjliga typer som en användare kan ersätta för en typ parameter.

## <a name="next-steps"></a>Nästa steg

Nu när du har sett alla typer som omfattar Q# språket, se [Skriv uttryck Q# i](xref:microsoft.quantum.guide.expressions) för att lära dig hur du skapar och ändrar uttryck för dessa olika typer.
