---
title: 'Q # typ modell | Microsoft Docs'
description: Modell av Q#-typ
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871642"
---
# <a name="the-type-model"></a>Typ modellen

Det här avsnittet innehåller en modell av typen Q # och beskriver syntaxen för att ange och arbeta med typer.
Vi noterar att Q # är ett *starkt inskrivet* språk, så att en noggrann användning av dessa typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.

För att tillhandahålla starkast möjliga garantier är konverteringar mellan typer i Q # explicita med anrop till funktioner som uttrycker konverteringen. En rad olika funktioner tillhandahålls som en del av <xref:microsoft.quantum.convert>-namnområdet.
Omsändningar till kompatibla typer av andra händer implicit. 

Q # tillhandahåller båda primitiva typer, som kan användas direkt och en mängd olika sätt att skapa nya typer från andra typer.
Vi beskriver var och en i resten av det här avsnittet.

## <a name="primitive-types"></a>Primitiva typer

Q #-språket innehåller flera *primitiva typer*, från vilka andra typer kan konstrueras:

- `Int` typen representerar ett 64-bitars heltal, t. ex.: `2`, `107`, `-5`.
- `BigInt` typen representerar ett signerat heltal av godtycklig storlek, t. ex. `2L`, `107L`, `-5L`.
   Den här typen baseras på .NET-<xref:System.Numerics.BigInteger>
   bastyp.
- `Double` typen representerar ett flyttal med dubbel precision, t. ex.: `0.0`, `-1.3`, `4e-7`.
- `Bool` typen representerar ett booleskt värde som antingen kan vara `true` eller `false`.
- `Qubit` typen representerar en Quantum-bit eller qubit.
   `Qubit`s är ogenomskinlig för användaren. Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).
   Slutligen implementeras åtgärder på `Qubit`s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en simulering av detta).
- `Pauli` typen representerar en av de fyra Pauli-operatörerna med en qubit.
   Den här typen används för att beteckna bas operationen för rotationer och för att ange den som ska mätas.
   Detta är en uppräknings typ som har fyra möjliga värden: `PauliI`, `PauliX`, `PauliY`och `PauliZ`, som är konstanter av typen `Pauli`.
- `Result` typen representerar resultatet av ett mått.
   Detta är en uppräknings typ med två möjliga värden: `One` och `Zero`, som är konstanter av typen `Result`.
   `Zero` anger att + 1-eigenvalue mättes. `One` anger-1-eigenvalue.
- `Range` typen representerar en sekvens med heltal, som betecknas med `start..step..stop`, där du ser att steget är alternativ. 
   Det är `start .. stop` motsvarar `start..1..stop`, och till exempel `1..2..7` representerar sekvensen $\{1, 3, 5, 7\}$.
- `String` typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.
  Den här typen används för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.
- `Unit` typen är den typ som endast tillåter ett värde `()`. 
  Den här typen används för att indikera att funktionen Q # Function eller operation returnerar ingen information. 

Konstanterna `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`och `Zero` är alla reserverade symboler i Q #.

## <a name="array-types"></a>Mat ris typer

Med en giltig Q #-typ `'T`, finns en typ som representerar en matris med värden av typen `'T`.
Den här mat ris typen visas som `'T[]`. till exempel `Qubit[]` eller `Int[][]`.
Till exempel är en samling med heltal `Int[]`, medan en matris med matriser med `(Bool, Pauli)` värden anges `(Bool, Pauli)[][]`.

I det andra exemplet noterar du att detta representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris.
Q # ger inte stöd för rektangulära flerdimensionella matriser.

Ett mat ris värde kan skrivas i Q #-källkod med hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]`.
Typen av mat ris literal bestäms av den gemensamma bastypen för alla objekt i matrisen. 

> [!WARNING]
> Elementen i en matris kan inte ändras efter att matrisen har skapats.
> Du kan använda uttryck för att uppdatera och omtilldela och/eller kopiera och uppdatera för att skapa en modifierad matris.

Du kan också skapa en matris från dess storlek med hjälp av nyckelordet `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

I båda fallen kan Core-funktionen `Length` användas för att hämta antalet element som en `Int`när en matris har konstruerats.
Matriser kan användas tillsammans med hakparenteser, med under skript som antingen har typ `Int` eller typ `Range`, för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.
Under skripten för matriser är noll-baserade:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tuple-typer

För noll eller flera olika typer `T0`, `T1`,..., `Tn`, kan vi ange en ny *typ av tupel* som `(T0, T1, ..., Tn)`.
De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))`.
Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.

Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.
`(3, false)` är till exempel en tupel vars typ är Tuple-typen `(Int, Bool)`.
Det går att skapa matriser av tupler, tupler av matriser, tupler av under tupler osv.

Från och med Q # 0,3 är `Unit` namnet på den tomma tuplens *typ* . `()` används för det tomma tuple- *värdet*.

Tupel-instanser är oföränderliga.
Q # innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.

Tupler är ett kraftfullt koncept som används i Q # för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.
I synnerhet kan vi, om du använder tupel notation, uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.

### <a name="singleton-tuple-equivalence"></a>Jämförelse av singleton-tupel

Det går att skapa en singleton-tupel (Single-element), `('T1)`, till exempel `(5)` eller `([1,2,3])`.
Q # behandlar dock en singleton-tupel som är helt likvärdig med värdet för den omslutna typen.
Det innebär att det inte finns någon skillnad mellan `5` och `(5)`, eller mellan `5` och `(((5)))`, eller mellan `(5, (6))` och `(5, 6)`.

Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.
Det är bara att skriva `(5)+3` som ska skriva `5+3`, och båda uttrycken kommer att utvärderas till `8`.
Det innebär särskilt att en åtgärd eller funktion vars typ av tupel eller utgående tuple har ett fält kan betraktas som ett enda argument eller returnerar ett enda värde.

Vi refererar till denna egenskap som _likhet med singleton-tupel_.

## <a name="user-defined-types"></a>Användardefinierade typer

En Q #-fil kan definiera en ny namngiven typ som innehåller ett enda värde av juridisk typ.
För valfri tupel-typ `T`kan vi deklarera en ny användardefinierad typ som är en undertyp till `T` med `newtype`-instruktionen.
I @"microsoft.quantum.math"-namnrymden definieras komplexa tal som en användardefinierad typ:

```qsharp
newtype Complex = (Double, Double);
```

Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double`.   
Förutom anonyma objekt har användardefinierade typer även stöd för namngivna objekt från och med Q # version 0,7 eller senare. Vi kan till exempel ha namngett objekten till objekt `Re` för det dubbla som representerar den verkliga delen av ett komplext tal och `Im` för den imaginära delen: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds. Dessutom kan inre objekt namnges.
Typen `Nested` som definieras nedan har exempelvis en underliggande typ `(Double, (Int, String))`, varav bara objektet av typen `Int` har namngetts och alla andra objekt är anonyma. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Namngivna objekt har fördelen att de kan nås direkt via åtkomst operatören `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

För att få åtkomst till anonyma objekt, måste det omslutna värdet först extraheras med postfix-operatören `!`.
Med operatorn "unwrap" `!`kan du extrahera värdet som finns i en användardefinierad typ.
Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Unwrap-operatorn omger ett exakt rad brytnings lager.
Flera unwrap-operatorer kan användas för att få åtkomst till ett multiplicering-figursatt värde.

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

Ta en titt på avsnittet om att [packa upp uttryck](xref:microsoft.quantum.language.expressions#unwrap-expressions) och [operatorer prioritet](xref:microsoft.quantum.language.expressions#operator-precedence) för mer information.

Värdena för en användardefinierad typ kan skapas genom att anropa motsvarande typ-konstruktor:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Precis som för matriser kopierar sådana uttryck alla objekt värden för det ursprungliga uttrycket, med undantag för de angivna namngivna objekten. För dessa värden anges de som definierats till höger i uttrycket. Andra språk konstruktioner, t. ex. [uppdaterings-och omtilldelnings instruktioner](xref:microsoft.quantum.language.statements#update-and-reassign-statement), som är tillgängliga för mat ris objekt finns även för namngivna objekt i användardefinierade typer.

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

Det går inte att skapa rekursiva typ strukturer.
Det vill säga den typ som definierar en användardefinierad typ får inte vara en tuple-typ som innehåller ett element av den användardefinierade typen.
I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning typ definitioner skulle vara ogiltiga:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.
Om du återgår till exemplet på `Complex`kan en av dem också ha definierat 2D polär-koordinater som en användardefinierad typ:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Även om både `Complex` och `Polar` har en underliggande typ `(Double, Double)`är de två typerna helt inkompatibla i Q #, vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.
På så sätt har användardefinierade typer en liknande roll som poster i F# till exempel. 


## <a name="operation-and-function-types"></a>Åtgärds-och funktions typer

En Q #- _åtgärd_ är en Quantum-underrutin.
Det innebär att det är en anropningsbar rutin som innehåller kvantåtgärder.

_Funktionen_ Q # är en klassisk underrutin som används i en Quantum-algoritm.
Den kan innehålla en klassisk kod men inga Quantum-åtgärder.
Mer specifikt kan funktioner inte allokera eller låna qubits, och de kan inte anropa åtgärder.
Det går dock att skicka dem eller qubits för bearbetning.
Funktioner är därför helt deterministiska i den mening som anropar dem med samma argument kommer alltid att ge samma resultat. 

Tillsammans kallas åtgärder och funktioner _callables_.  Du kan se några [exempel](#examples) på dessa nedan.

Alla Q # callables anses ta ett enda värde som indata och returnera ett enda värde som utdata.
Både in-och utdata-värden kan vara tupler.
Callables som inte returnerar resultat `Unit`.
Callables som inte har något inmatade tar den tomma tuppeln som inmatad.

Den grundläggande typen för anrop är skriven som `('Tinput => 'Tresult)` eller `('Tinput -> 'Tresult)`, där både `'Tinput` och `'Tresult` är typer.
Det första formuläret, med `=>`, används för åtgärder. det andra formuläret, med `->`, för functions.
`((Qubit, Pauli) => Result)` representerar till exempel signaturen för en möjlig mätnings åtgärd med en qubit.

Funktions typer anges fullständigt av signaturen.
En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)`.

Åtgärder – men inte Functions – har vissa ytterligare _Egenskaper_ som uttrycks som en del av åtgärds typen. Dessa egenskaper innehåller information om vad functors åtgärden stöder.
Functors är meta-åtgärder som genererar en specialisering av en bas åtgärd. Se [Functors](#functors)nedan.

Åtgärds typer anges av deras typ av Indatatyp, Utdatatyp och deras egenskaper.    
För att kunna kräva stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ, måste vi lägga till en anteckning som anger motsvarande egenskaper.
En antecknings `is Ctl` till exempel anger att åtgärden är kontrollerbar. Om vi vill kräva att en åtgärd av den typen stöder både `Adjoint` och `Controlled` Functor kan vi uttrycka detta som `(Qubit => Unit is Adj + Ctl)`. De använda åtgärds egenskaperna `Adj` och `Ctl` strikta tal är två fördefinierade uppsättningar med etiketter, där varje etikett anger en viss åtgärds egenskaper som t. ex. stöd för en viss Functor.
Därför används `+` för att ange union av dessa två uppsättningar och `*` används för att ange skärnings punkten – d.v.s. de etiketter som är gemensamma för båda uppsättningarna.  

Till exempel har Pauli `X`-åtgärden typ `(Qubit => Unit is Adj + Ctl)`.
En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.


### <a name="type-parameterized-functions-and-operations"></a>Typ-parameter funktioner och åtgärder

Typer som kan anropas kan innehålla typ parametrar.
Typ parametrar anges med en symbol som föregås av ett enkelt citat tecken. till exempel är `'A` en juridisk typ parameter.

En typ parameter kan visas mer än en gång i en enda signatur.
En funktion som till exempel tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signaturen `(('A[], 'A->'A) -> 'A[])`.
På samma sätt kan en funktion som returnerar sammansättningen av två åtgärder ha signatur `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

När du anropar en typ-parameter anrops bara, måste alla argument som har samma typ parameter vara av samma typ.

Q # innehåller ingen mekanism för att begränsa de möjliga typer som kan ersättas av en typ parameter.

### <a name="type-compatibility"></a>Skriv kompatibilitet

En åtgärd med ytterligare functors som stöds kan användas överallt där en åtgärd har färre functors men samma signatur förväntas.
Till exempel kan en åtgärd av typen `(Qubit => Unit is Adj)` användas överallt där en åtgärd av typen `(Qubit => Unit)` förväntas.

Q # är samvariant med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med en typ som kan anropas med samma Indatatyp och en resultat typ som `'A` är kompatibel med.

Q # är contravariant med avseende på indatatyper: ett anrop som tar en typ `'A` som inmatare är kompatibel med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A`.

Det innebär att man får följande definitioner:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

följande är sant:

- Funktionen `ConjugateInvertWith` kan anropas med ett `inner` argument för antingen `Invert` eller `ApplyUnitary`.
- Funktionen `ConjugateUnitaryWith` kan anropas med ett `inner` argument av `ApplyUnitary`, men inte `Invert`.
- Ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` kan returneras från `ConjugateInvertWith`.

> [!IMPORTANT]
> I Q # 0,3 införs en betydande skillnad i beteendet för användardefinierade typer.

Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.
Det innebär att ett värde för en användardefinierad typ inte kan användas om ett värde av den underliggande typen förväntas.

### <a name="functors"></a>Functors

En Functor i Q # är en fabrik som definierar en ny åtgärd från en annan åtgärd.
Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.
Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå.

Functors har ingen representation i Q #-typ systemet. Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument. 

En Functor används genom att tillämpa den på en åtgärd och returnera en ny åtgärd.
Till exempel skrivs åtgärden som resulterar i att använda `Adjoint`-Functor till `Y`-åtgärden som `Adjoint Y`.
Den nya åtgärden kan sedan anropas som vilken annan åtgärd som helst.
Därför använder `Adjoint Y(q1)` det intilliggande Functor till åtgärden `Y` för att generera en ny åtgärd och tillämpar den nya åtgärden på `q1`.

På samma sätt tillämpar `Controlled X(controls, target)` kontrollerade Functor i `X`-åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden på `controls` och `target`.

De två standard functors i Q # är `Adjoint` och `Controlled`.

#### <a name="adjoint"></a>Angränsande

I Quantum Computing är det angränsande av en åtgärd den komplexa konjugatet för åtgärden.
För åtgärder som implementerar en enhetlig operatör är det intilliggande inversen till åtgärden.
För en enkel åtgärd som bara anropar en sekvens med andra enhetliga åtgärder på en uppsättning qubits, kan det intilliggande värdet beräknas genom att använda angränsande åtgärder på samma qubits i omvänd ordning.

Med ett åtgärds uttryck kan ett nytt åtgärds uttryck skapas med hjälp av `Adjoint` Functor.
`Adjoint QFT` anger till exempel den angränsande av `QFT` åtgärden.
Den nya åtgärden har samma signatur och typ som bas åtgärd.
I synnerhet tillåter den nya åtgärden också `Adjoint`, och kommer att tillåta `Controlled` om och endast om bas åtgärden har utförts.

Det intilliggande Functor är en egen invertering; det vill säga `Adjoint Adjoint Op` alltid är detsamma som `Op`.

#### <a name="controlled"></a>Styr

Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.
Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.
Därmed används kontrollerade åtgärder ofta för att generera entanglement.

I Q # tar kontrollerade versioner alltid en matris med Control-qubits, och det angivna läget är alltid för alla kontroll qubits att vara i`PauliZ`beräknings `One`s status $ \ket{1}$.
Kontroll som bygger på andra tillstånd kan uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.
Om du till exempel använder en `X`-åtgärd för en kontroll qubit före och efter en kontrollerad åtgärd, kommer åtgärden att kontrol lera `Zero` tillstånd ($ \ket{0}$) för qubit; att tillämpa en `H`-åtgärd innan och efter styrs av `PauliX` `One` tillstånd, det vill säga 1 eigenvalue av Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ i stället för `PauliZ` `One`-tillstånd.

Med ett åtgärds uttryck kan ett nytt åtgärds uttryck skapas med hjälp av `Controlled` Functor.
Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.
Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.
Den nya åtgärden stöder `Controlled`och har stöd för `Adjoint` om och bara om den ursprungliga åtgärden utfördes.

Om den ursprungliga åtgärden bara tog ett enda argument, kommer singleton-tupel att visas här.
`Controlled X` är till exempel den kontrollerade versionen av `X` åtgärden.
`X` har typen `(Qubit => Unit is Adj + Ctl)`, så `Controlled X` har typen `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; på grund av singleton tuple-motsvarighet är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.
`Controlled Rz` är till exempel den kontrollerade versionen av `Rz` åtgärden.
`Rz` har typen `((Double, Qubit) => Unit is Adj + Ctl)`, så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Därför är `Controlled Rz(controls, (0.1, target))` ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target`).

I ett annat exempel kan `CNOT(control, target)` implementeras som `Controlled X([control], target)`. Om ett mål ska styras av 2 Control qubits (CCNOT) kan vi använda `Controlled X([control1, control2], target)` instruktion.

### <a name="examples"></a>Exempel

Det här exemplet på en Q #-åtgärd kommer från [mått](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) exemplet. Inom åtgärder kan vi allokera qubits och använda Quantum-åtgärder på dessa qubits, till exempel `H` och `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Det här exemplet på en funktion kommer från [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) -exemplet. Den innehåller en helt klassisk kod. Du kan se att, till skillnad från exemplet ovan, inga qubits har tilldelats och inga Quantum-åtgärder används.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Det är också möjligt att en funktion skickas qubits för bearbetning, som i det här exemplet från [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) -exemplet. Qubits skickas till funktionen och används för bearbetning, men vid ingen tidpunkt modifieras qubit-tillstånden.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
