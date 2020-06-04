---
title: 'Skriv uttryck i Q #'
description: 'Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: c4b2cc0bed44ffdfb191ba522d6526959e7c6708
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327313"
---
# <a name="type-expressions-in-q"></a>Skriv uttryck i Q #

## <a name="numeric-expressions"></a>Numeriska uttryck

Numeriska uttryck är uttryck av typen `Int` , `BigInt` eller `Double` .
Det vill säga att de är antingen heltals-eller flytt ALS nummer.

`Int`litteraler i Q # skrivs enkelt som en följd av siffror.
Hexadecimala och binära heltal stöds med `0x` `0b` prefixet respektive.

`BigInt`litteraler i Q # skrivs med ett efterföljande `l` eller `L` suffix.
Hexadecimala Big heltal stöds med ett "0x"-prefix.
Det innebär att följande är giltig användning av `BigInt` litteraler:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`litteraler i Q # är flytt ALS siffror som skrivs med decimal siffror.
De kan skrivas med ett decimal tecken, `.` och/eller en exponentiell del som anges med "e" eller "e" (efter vilken endast ett möjligt negativt tecken och decimal siffror är giltiga).
Följande är giltiga `Double` litteraler: `0.0` , `1.2e5` , `1e-5` .

Med ett mat ris uttryck för valfri element typ `Int` kan ett uttryck skapas med hjälp av den [`Length`](xref:microsoft.quantum.core.length) inbyggda funktionen, med mat ris uttrycket omslutna i parentes `(` och `)` .
Om till exempel är `a` kopplat till en matris, `Length(a)` är ett heltals uttryck.
Om `b` är en matris med heltals matriser, `Int[][]` `Length(b)` är antalet underordnade matriser i `b` och `Length(b[1])` är antalet heltal i den andra under matrisen i `b` .

Två numeriska uttryck av samma typ, de binära operatorerna `+` , `-` , `*` och `/` kan användas för att skapa ett nytt numeriskt uttryck.
Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.

Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.
På samma sätt `^` kan användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.
Slutligen `^` kan du använda ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.
I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.

Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big-heltals uttryck skapas med `%` operatörerna (Modulus), `&&&` (bitvis and), `|||` (bitvis or) eller `^^^` (Bitvis XOR).

Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till höger, `<<<` kan operatorerna (aritmetisk vänster Shift) eller `>>>` (aritmetiska höger Shift) användas för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.

Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.
Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.
Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet, det vill säga `mod 64` en skift på 1 och en förskjutning på 65 har samma resultat.

För både heltals-och Big heltals värden är skiften aritmetiska.
Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.
Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.

Heltals Division och heltals-Modulus följer samma beteende för negativa tal som C#.
Det vill säga `a % b` har alltid samma signera som och är `a` `b * (a / b) + a % b` alltid lika med `a` .
Ett exempel:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Big Integer-Division och Modulus fungerar på samma sätt.

Ett nytt uttryck kan skapas med hjälp av ett numeriskt uttryck med hjälp av den `-` unära operatorn.
Det nya uttrycket är av samma typ som komponent uttrycket.

Med alla heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med den `~~~` unära operatorn (bitvis komplement).

## <a name="boolean-expressions"></a>Booleska uttryck

De två `Bool` literala värdena är `true` och `false` .

Om du har två uttryck av samma primitiva typ `==` kan de och `!=` binära operatorerna användas för att skapa ett `Bool` uttryck.
Uttrycket är sant om de två uttrycken är lika och falskt om inte.

Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras. Du kan till exempel använda operatorn "unwrap" `!` (förklaras i detalj på [typer i Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)).

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Likhets jämförelse för `Qubit` värden är identitets likhet, det vill säga om de två uttrycken identifierar samma qubit.
Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.

Jämförelse av `Double` värden kan vara missvisande på grund av avrundnings effekter.
Till exempel `49.0 * (1.0/49.0) != 1.0` .

Två numeriska uttryck, de binära operatorerna,, `>` `<` `>=` och `<=` kan användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.

Med två booleska uttryck `and` kan de och `or` binära operatorerna användas för att skapa ett nytt booleskt uttryck som är sant om båda uttrycken (ansvars båda eller båda) är sanna.

Med alla booleska uttryck kan den `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.

## <a name="string-expressions"></a>Sträng uttryck

Q # tillåter att strängar används i `fail` instruktionen (förklaras i [kontroll flödet](xref:microsoft.quantum.guide.controlflow#fail-statement)) och i [`Message`](xref:microsoft.quantum.intrinsic.message) funktionen standard.
Det speciella beteendet för den senare beror på vilken simulator som används, men skriver vanligt vis ett meddelande till värd konsolen när den anropas under ett Q #-program.

Strängar i Q # är antingen litteraler eller interpolerade strängar.

Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode-tecken som omges av dubbla citat tecken `"` .
I en sträng kan back snedstrecket `\` användas för att undvika ett dubbelt citat tecken och för att infoga en ny rad som `\n` , en vagn retur som `\r` och en flik som `\t` .
Till exempel:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Interpolerade strängar

Q #-syntaxen för String-interpolation är en delmängd av C#-syntaxen, men vi sammanfattar här viktiga punkter som de gäller för Q #.
De huvudsakliga distinkta beskrivs nedan.

För att identifiera en tecken sträng som en interpolerad sträng, lägga den med `$` symbolen.
Det går inte att ha blank steg mellan `$` och `"` som startar en tecken sträng.

Följande är ett grundläggande exempel [`Message`](xref:microsoft.quantum.intrinsic.message) som använder funktionen för att skriva resultatet av en mätning till-konsolen, tillsammans med andra Q #-uttryck.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.

Du hittar mer information om C#-syntaxen i [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
Den mest viktiga skillnaden är att Q # inte stöder orda Grant-interpolerade strängar (multi-line).
Uttryck i en interpolerad sträng följer Q # syntax, inte C#-syntax.

## <a name="range-expressions"></a>Intervall uttryck

Alla tre `Int` uttryck `start` , `step` , och `stop` , `start .. step .. stop` är ett intervall uttryck vars första element är, det `start` andra elementet är `start+step` , det tredje elementet, `start+step+step` osv., tills `stop` det skickas.
Ett intervall kan vara tomt om, t. ex. `step` är positivt och `stop < start` .
Det sista elementet i intervallet är `stop` om skillnaden mellan `start` och `stop` är en integral multipel av, det vill säga `step` intervallet i båda ändar.

Två uttryck har `Int` angetts `start` och `stop` `start .. stop` är ett intervall uttryck som är lika med `start .. 1 .. stop` .
Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start` . i så fall är intervallet tomt.

Några exempel intervall är:

- `1..3`är intervallet 1, 2, 3.
- `2..2..5`är intervallet 2, 4.
- `2..2..6`är intervallet 2, 4, 6.
- `6..-2..2`är intervallet 6, 4, 2.
- `2..1`är det tomma intervallet.
- `2..6..7`är intervallet 2.
- `2..2..1`är det tomma intervallet.
- `1..-1..2`är det tomma intervallet.

## <a name="qubit-expressions"></a>Qubit-uttryck

De enda `Qubit` uttrycken är symboler som är kopplade till `Qubit` värden eller mat ris element `Qubit` .
Det finns inga `Qubit` litteraler.

## <a name="pauli-expressions"></a>Pauli-uttryck

De fyra `Pauli` värdena, `PauliI` , `PauliX` , `PauliY` och `PauliZ` , är giltiga `Pauli` uttryck.

Förutom så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element `Pauli` .

## <a name="result-expressions"></a>Resultat uttryck

De två `Result` värdena `One` och `Zero` , är giltiga `Result` uttryck.

Förutom så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element `Result` .
Observera särskilt att `One` inte är detsamma som heltalet `1` och det finns ingen direkt konvertering mellan dem.
Samma sak gäller `Zero` och `0` .

## <a name="tuple-expressions"></a>Tuple-uttryck

En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges av `(` och `)` .
Är till exempel `(1, One)` ett `(Int, Result)` uttryck.

Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.

## <a name="user-defined-type-expressions"></a>Användardefinierade typ uttryck

En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.
Om är till exempel `IntPair` en användardefinierad typ som baseras på, är `(Int, Int)` `IntPair(2, 3)` en giltig litteral av den typen.

Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.

## <a name="unwrap-expressions"></a>Packa upp uttryck

I Q # är unwrap-operatorn ett avslutande utrops tecken `!` .
Om är till exempel `IntPair` en användardefinierad typ med underliggande typ `(Int, Int)` och `s` var en variabel med värde `IntPair(2, 3)` , `s!` skulle det vara `(2, 3)` .

För användardefinierade typer definieras i termer av andra användardefinierade typer. den avbrytande operatorn kan upprepas. `s!!`anger t. ex. dubblerat-värde för `s` .
Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair` och `t` är en variabel med värde `WrappedPair(IntPair(1,2))` , blir `t!!` det alltså `(1,2)` .

`!`Operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.
`!`och `[]` BIND positions läge, som är, `a[i]![3]` ska läsas som `((a[i])!)[3]` : ta det `i` "th"-elementet i `a` , packa upp det och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).

Prioriteten hos `!` operatorn har en effekt som kanske inte är uppenbar.
Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.
Ett exempel:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Mat ris uttryck

En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som omges av `[` och `]` .
Alla element måste vara kompatibla med samma typ.

Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.
Till exempel `[1,2,3] + [4,5,6]` är `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Skapa matris

Med en typ och ett `Int` uttryck `new` kan operatorn användas för att allokera en ny matris med den aktuella storleken.
Allokera till exempel `new Int[i + 1]` en ny `Int` matris med `i + 1` element.

Tomma mat ris strängar, `[]` tillåts inte.
I stället använda `new ★[0]` , där `★` är plats hållare för lämplig typ, kan du skapa den önskade matrisen med längden noll.

Elementen i en ny matris initieras till ett typ beroende standardvärde.
I de flesta fall är detta en variation på noll.

Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.
Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.
Detta liknar en null-referens i språk som C# eller Java.
Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt. Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays> .

Standardvärdena för varje typ är:

Typ | Standard
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Ogiltig qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Det tomma intervallet,`1..1..0`
 `Callable` | _Ogiltigt anrops bara_
 `Array['T]` | `'T[0]`

Tuple-typer är initierade element-by-element.


### <a name="array-elements"></a>Mat ris element

Med ett mat ris uttryck och ett `Int` uttryck kan ett nytt uttryck skapas med `[` `]` operatorn och array element-operatorn.
Det nya uttrycket är av samma typ som matrisens element typ.
Om till exempel är `a` kopplat till en matris med `Double` s, `a[4]` är ett `Double` uttryck.

Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.
Om `a` och `b` är båda matriserna i `Int` s, uttrycks t. ex. ett element från sammanfogningen:

```qsharp
(a + b)[13]
```

Alla matriser i Q # är noll-baserade.
Det vill säga det första elementet i en matris `a` är alltid `a[0]` .


### <a name="array-slices"></a>Mat ris segment

Med ett mat ris uttryck och ett `Range` uttryck kan ett nytt uttryck skapas med `[` `]` operatorn array och array.
Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen i `Range` , i den ordning som definieras av `Range` .
Om till exempel är `a` kopplat till en matris med `Double` s, `a[3..-1..0]` är ett `Double[]` uttryck som innehåller de första fyra elementen i, `a` men i omvänd ordning som de visas i `a` .

Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.

Precis som med referenser till mat ris element, om mat ris uttrycket inte är en enkel identifierare, måste det omges av parenteser för att kunna segmentera.
Om `a` och `b` är båda matriserna i `Int` s, uttrycks en sektor från sammanfogningen som:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Uppskjutna start-/slut värden

Från och med vår 0,8-utgåva stöder vi sammanhangsbaserade uttryck för intervall segmentering. I synnerhet kan intervall start-och slut värden utelämnas i kontexten för ett intervall segment uttryck. I så fall kommer kompileraren att tillämpa följande regler för att härleda de avsedda avgränsarna för intervallet. 

Om start värde för intervall t. ex. utelämnas används värdet för uppskjutet start värde 
- är noll om inget steg har angetts eller det angivna steget är positivt och 
- är längden på den segmenterade matrisen minus en om det angivna steget är negativt. 

Om slutvärdet för intervallet utelämnas visas värdet för det härledda slut värdet 
- är längden på den segmenterade matrisen minus ett om inget steg har angetts eller om det angivna steget är positivt och 
- är noll om det angivna steget är negativt. 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Kopiera och uppdatera uttryck

Eftersom alla Q #-typer är värde typer, där qubits tar en lite speciell roll, skapas en "kopia" när ett värde är kopplat till en symbol eller när en symbol har bundits. Detta är att säga att Q # är detsamma som om en kopia skapades för tilldelningen.
Naturligtvis i praktiken är det bara de relevanta delarna som faktiskt återskapas vid behov. 

Detta omfattar även matriser.
I synnerhet är det inte möjligt att uppdatera mat ris objekt. Om du vill ändra en befintlig matris måste du använda en *kopierings-och-uppdaterings* funktion.

Nya matriser kan skapas från befintliga med hjälp av *kopierings-och-uppdatera-* uttryck.
Ett kopierings-och-uppdatering-uttryck är ett uttryck för formuläret `expression1 w/ expression2 <- expression3` , där `expression1` måste vara av typen av `T[]` viss typ `T` .
Den andra `expression2` definierar indexen för de element som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen `Range` .
Om `expression2` är av typen `Int` måste `expression3` vara av typen `T` . Om `expression2` är av typen `Range` måste `expression3` vara av typen `T[]` .

Ett Copy-och-Update-uttryck `arr w/ idx <- value` skapar en ny matris med alla element som har angetts till motsvarande-element i `arr` , förutom elementen på `idx` , som är inställda på en/ett i `value` . Om t. ex. `arr` innehåller en matris `[0,1,2,3]` , 
- `arr w/ 0 <- 10`är matrisen `[10,1,2,3]` .
- `arr w/ 2 <- 10`är matrisen `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`är matrisen `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Kopiera och uppdatera uttryck för namngivna objekt

Det finns liknande uttryck för namngivna objekt i användardefinierade typer. 

Överväg till exempel typen 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Om `c` innehåller värdet av typen `Complex(1., -1.)` `c w/ Re <- 0.` är det ett uttryck av typen `Complex` som utvärderas till `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Ojämna matriser

En taggad matris, som ibland kallas matriser, är en matris vars element är matriser.
Elementen i en taggad matris kan ha olika storlekar.
I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Matriser med callables 

Observera att det finns mer information om typer som kan anropas nedan, samt på nästa sida, [åtgärder och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions).

Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.
Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.
Till exempel, `Op1` `Op2` , och `Op3` alla `Qubit[] => Unit` , men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:

- `[Op1, Op2]`är en matris med `(Qubit[] => Unit)` åtgärder.
- `[Op1, Op3]`är en matris med `(Qubit[] => Unit is Adj)` åtgärder.
- `[Op2, Op3]`är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.

Men medan `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` -åtgärder har den vanligaste bastypen för `(Qubit[] => Unit)` , Observera att matriser *för* dessa operatörer inte delar en gemensam bastyp. Skulle till exempel `[[Op1], [Op2]]` kunna generera ett fel eftersom det försöker skapa en matris av de inkompatibla mat ris typerna `(Qubit[] => Unit is Adj)[]` och `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Villkors uttryck

Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|` .
Till exempel `a==b ? c | d` .
I det här exemplet är värdet för villkors uttrycket `c` IF `a==b` sant och `d` om det är falskt.

### <a name="conditional-expressions-with-callables"></a>Villkors uttryck med callables

De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.
I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.
Till exempel, `Op1` `Op2` , och `Op3` alla `Qubit[]=>Unit` , men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:

- `flag ? Op1 | Op2`är en `(Qubit[] => Unit)` åtgärd.
- `flag ? Op1 | Op3`är en `(Qubit[] => Unit is Adj)` åtgärd.
- `flag ? Op2 | Op3`är en `(Qubit[] => Unit is Ctl)` åtgärd.

Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.
Om är till exempel, `a==b ? C(qs) | D(qs)` om `a==b` är sant `C` , kommer åtgärden att anropas och om den är false `D` anropas bara.
Detta liknar korta kretsar på andra språk.

## <a name="callable-expressions"></a>Anrops bara uttryck

En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.
Är till exempel `X` en åtgärds-literal som refererar till standard biblioteks `X` åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.

Om en åtgärd har stöd för `Adjoint` Functor `Adjoint op` är ett åtgärds uttryck.
På samma sätt `Controlled` `Controlled op` är det ett åtgärds uttryck om åtgärden stöder Functor.
Typerna av de här uttrycken anges i specialisering för att [anropa en åtgärd](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Functors ( `Adjoint` och `Controlled` ) binder mer nära varandra än alla andra operatorer, förutom unwrap-operatorn `!` och mat ris indexering med [] ".
Därför är följande alla juridiska, förutsatt att de åtgärder som har stöd för de functors som används:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Typ-parametriserade anrops bara uttryck

En anrops bara literal kan användas som ett värde, t. ex. tilldela en variabel eller skicka till ett annat anrop.
I det här fallet, om anropet har [typ parametrar](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), måste de anges som en del av det anropade värdet.
Ett anrops bara värde kan inte ha ospecificerade typ parametrar.

Om är till exempel `Fun` en funktion med signatur `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Anrops anrops anrops uttryck

Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.
Typen av anrops uttryck är utdatatypen för den anropande signaturen.

Om är till exempel en `Op` åtgärd med signatur `((Int, Qubit) => Double)` , `Op(3, qubit1)` är ett uttryck av typen `Double` .
På samma sätt, om `Sin` är en funktion med signatur `(Double -> Double)` , `Sin(0.1)` är ett uttryck av typen `Double` .
Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))` , `Builder(3)` är en funktion från till int.

Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.
För att anropa resultatet av anrop `Builder` från föregående stycke är därför rätt syntax:

```qsharp
(Builder(3))(2)
```

När du anropar en [typ-parameter](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.
Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.
*Det krävs* dock för [partiella program](xref:microsoft.quantum.guide.operationsfunctions#partial-application) om ett argument av typen parameter lämnas ospecificerade.
Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.

Om har exempelvis signatur och har signatur, `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` och `Op3` har signatur `(Qubit[] => Unit)` , för att anropa `Func` med `Op1` som första argument, `Op2` som den andra, och `Op3` som tredje:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.


## <a name="operator-precedence"></a>Prioritet för Operator

Alla binära operatorer är rätt associerade, förutom för `^` .

Hakparenteser `[` och `]` , för mat ris segmentering och indexering, bind före valfri operator.

Functors `Adjoint` och `Controlled` BIND efter mat ris indexering, men före alla andra operatorer.

Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.

Operatorer i prioritetsordning, från högsta till lägsta:

Operator | Ariteten | Description | Operands typer
---------|----------|---------|---------------
 avslutande`!` | Enställig | Packa upp | Valfri användardefinierad typ
 `-`, `~~~`, `not` | Enställig | Numeriskt negativ, bitvis komplement, logisk negation | `Int`, `BigInt` eller `Double` för `-` , `Int` eller `BigInt` `~~~` för `Bool``not`
 `^` | Binär | Heltals effekt | `Int`eller `BigInt` för basen `Int` för exponenten
 `/`, `*`, `%` | Binär | Division, multiplikation, heltals-modulus | `Int`, `BigInt` eller `Double` för `/` och `*` , `Int` eller `BigInt` för`%`
 `+`, `-` | Binär | Kombination av addition eller sträng och matris, subtraktion | `Int``BigInt`eller `Double` , även `String` eller valfri mat ris typ för`+`
 `<<<`, `>>>` | Binär | Vänster SKIFT, höger Skift | `Int` eller `BigInt`
 `<`, `<=`, `>`, `>=` | Binär | Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser | `Int``BigInt`eller`Double`
 `==`, `!=` | Binär | lika med, inte lika med jämförelser | vilken primitiv typ som helst
 `&&&` | Binär | Bitvis och | `Int` eller `BigInt`
 `^^^` | Binär | Bitvis XOR | `Int` eller `BigInt`
 <code>\|\|\|</code> | Binär | Bitvis eller | `Int` eller `BigInt`
 `and` | Binär | Logiskt AND | `Bool`
 `or` | Binär | Logiskt OR | `Bool`
 `..` | Binär/ternär | Intervall operator | `Int`
 `?` `|` | Ternär | Villkorsstyrd | `Bool`för den vänstra sidan
`w/` `<-` | Ternär | Kopiera och uppdatera | Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)

## <a name="next-steps"></a>Nästa steg

Nu när du kan arbeta med uttryck i Q # kan du gå till [åtgärder och funktioner i q #](xref:microsoft.quantum.guide.operationsfunctions) för att lära dig hur du definierar och anropar-åtgärder och-funktioner.
