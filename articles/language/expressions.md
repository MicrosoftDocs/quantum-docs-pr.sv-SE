---
title: Uttryck | Microsoft Docs
description: Uttryck
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185213"
---
# <a name="expressions"></a>Uttryck

## <a name="grouping"></a>Baserat

Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.
`(7)` är till exempel ett `Int` uttryck, `([1,2,3])` är ett uttryck av typen matris med `Int`s och `((1,2))` är ett uttryck med typ `(Int, Int)`.

Motsvarigheten mellan enkla värden och tupler med ett enda element som beskrivs i [typ modellen](xref:microsoft.quantum.language.type-model#tuple-types) tar bort tvetydigheten mellan `(6)` som en grupp och `(6)` som en tupel med ett enda element.

## <a name="symbols"></a>Specialtecken

Namnet på en symbol som är kopplad till eller tilldelats ett värde av typen `'T` är ett uttryck av typen `'T`.
Om till exempel symbolen `count` är kopplad till heltal svärdet `5`, är `count` ett heltals uttryck.

## <a name="numeric-expressions"></a>Numeriska uttryck

Numeriska uttryck är uttryck av typen `Int`, `BigInt`eller `Double`.
Det vill säga att de är antingen heltals-eller flytt ALS nummer.

`Int` litteraler i Q # är identiska med heltals strängar i C#, förutom att ingen efterföljande "l" eller "l" krävs (eller tillåts).
Hexadecimala och binära heltal stöds med prefixet "0x" och "0b".

`BigInt` litteraler i Q # är identiska med Big heltals strängar i .NET, med ett efterföljande "l" eller "L".
Hexadecimala Big heltal stöds med ett "0x"-prefix.
Därför är följande giltiga användnings områden för `BigInt` litteraler:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` litteraler i Q # är identiska med dubbla strängar i C#, förutom att ingen efterföljande "d" eller "d" krävs (eller tillåts).

Med ett mat ris uttryck för valfri element typ kan ett `Int` uttryck skapas med hjälp av den inbyggda funktionen `Length`, med mat ris uttrycket omsluts av parenteser, `(` och `)`.
Om `a` till exempel är kopplat till en matris, är `Length(a)` ett heltals uttryck.
Om `b` är en matris med heltals matriser `Int[][]``Length(b)` är antalet underordnade matriser i `b`och `Length(b[1])` är antalet heltal i den andra under matrisen i `b`.

Med två numeriska uttryck av samma typ kan de binära operatorerna `+`, `-`, `*`och `/` användas för att skapa ett nytt numeriskt uttryck.
Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.

Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.
På samma sätt kan `^` användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.
Slutligen kan `^` användas med ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.
I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.

Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big-heltals uttryck skapas med operatorerna `%` (Modulus), `&&&` (bitvis AND), `|||` (bitvis OR) eller `^^^` (Bitvis XOR).

Med ett heltals uttryck eller ett Big-uttryck till höger, och ett heltals uttryck till höger, kan `<<<` (aritmetiska vänstra Shift) eller `>>>` (aritmetiska höger Shift) operatörer användas för att skapa ett nytt uttryck med samma typ som vänster uttryck.

Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.
Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.
Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet `mod 64`; det vill säga en skift på 1 och en förskjutning på 65 har samma resultat.

För både heltals-och Big heltals värden är skiften aritmetiska.
Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.
Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.

Heltals Division och heltals-Modulus följer samma beteende för negativa C#tal som.
Det vill `a % b` alltid ha samma tecken som `a`och `b * (a / b) + a % b` är alltid lika med `a`.
Exempel:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Big Integer-Division och Modulus fungerar på samma sätt.

Med ett numeriskt uttryck kan ett nytt uttryck skapas med hjälp av `-` unära operatorn.
Det nya uttrycket är av samma typ som komponent uttrycket.

Med ett heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med den unära operatorn `~~~` (bitvis komplement).

## <a name="boolean-expressions"></a>Booleska uttryck

De två `Bool` literala värdena är `true` och `false`.

Med två uttryck av samma primitiva typ kan `==` och `!=` binära operatorer användas för att skapa ett `Bool`-uttryck.
Uttrycket är sant om de två uttrycken är (ansvars värde) lika.

Värden för användardefinierade typer kan inte jämföras, endast deras värden kan jämföras. Exempel:

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Likhets jämförelse för `Qubit` värden är identitets likhet; det vill säga om de två uttrycken identifierar samma qubit.
Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.

Likhets jämförelse för `Double` värden kan vara missvisande på grund av avrundnings effekter.
`49.0 * (1.0/49.0) != 1.0`till exempel.

Med två numeriska uttryck kan de binära operatorerna `>`, `<`, `>=`och `<=` användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.

Med de två booleska uttrycken kan `and` och `or` binära operatorer användas för att skapa ett nytt booleskt uttryck som är sant om båda av (ansvars båda eller båda) de två uttrycken är sanna.

Med alla booleska uttryck kan `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.

## <a name="string-expressions"></a>Sträng uttryck

Q # tillåter att strängar används i `fail`-instruktionen och `Log` standard-funktionen.

Strängar i Q # är antingen litteraler eller interpolerade strängar.
Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode-tecken som omges av dubbla citat tecken `"`.
I en sträng kan du använda det omvända snedstrecket `\` för att undvika ett dubbelt citat tecken och infoga en ny rad som `\n`, en vagn retur som `\r`och en flik som `\t`.
Exempel:

```qsharp
"\"Hello world!\", she said.\n"
```

Q #-syntaxen för String-interpolation är en delmängd av C# 7,0-syntaxen. Q # stöder inte orda Grant (multi-line) interpolerade strängar.
Se [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) för C# syntaxen.

Uttryck i en interpolerad sträng följer Q # syntax, inte C# syntax.
Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.

## <a name="qubit-expressions"></a>Qubit-uttryck

De enda `Qubit` uttrycken är symboler som är kopplade till `Qubit` värden eller mat ris element i `Qubit` matriser.
Det finns inga `Qubit` litteraler.

## <a name="pauli-expressions"></a>Pauli-uttryck

De fyra `Pauli` värdena, `PauliI`, `PauliX`, `PauliY`och `PauliZ`är alla giltiga `Pauli` uttryck.

Andra än så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element i `Pauli` matriser.

## <a name="result-expressions"></a>Resultat uttryck

De två `Result` värdena `One` och `Zero`är giltiga `Result` uttryck.

Andra än så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element i `Result` matriser.
Observera särskilt att `One` inte är samma som det heltal som `1`, och det inte finns någon direkt konvertering mellan dem.
Detsamma gäller för `Zero` och `0`.

## <a name="range-expressions"></a>Intervall uttryck

Med de tre `Int` uttrycken `start`, `step`och `stop`, är `start .. step .. stop` ett intervall uttryck vars första element är `start`, det andra elementet är `start+step`, det tredje elementet är `start+step+step`osv., tills `stop` skickas.
Ett intervall kan vara tomt om till exempel `step` är positivt och `stop < start`.
Det sista elementet i intervallet är `stop` om skillnaden mellan `start` och `stop` är en integral multipel av `step`; det vill säga att intervallet inkluderas i båda ändar.

Under vissa två `Int` uttryck `start` och `stop`är `start .. stop` ett intervall uttryck som är lika med `start .. 1 .. stop`.
Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start`; i sådana fall är intervallet tomt.

Några exempel intervall är:

- `1..3` är intervallet 1, 2, 3.
- `2..2..5` är intervallet 2, 4.
- `2..2..6` är intervallet 2, 4, 6.
- `6..-2..2` är intervallet 6, 4, 2.
- `2..1` är det tomma intervallet.
- `2..6..7` är intervallet 2.
- `2..2..1` är det tomma intervallet.
- `1..-1..2` är det tomma intervallet.

## <a name="callable-expressions"></a>Anrops bara uttryck

En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.
`X` är till exempel en åtgärds-literal som refererar till standard biblioteket `X`-åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.

Om en åtgärd stöder `Adjoint` Functor är `Adjoint op` ett åtgärds uttryck.
På samma sätt, om åtgärden har stöd för `Controlled` Functor, är `Controlled op` ett åtgärds uttryck.
Typerna av dessa uttryck anges i [Functors](xref:microsoft.quantum.language.type-model#functors).

Functors (`Adjoint` och `Controlled`) binder mer nära varandra än alla andra operatorer, förutom unwrap-operatorn `!` och mat ris indexering med `[]`.
Därför är följande alla juridiska, förutsatt att de åtgärder som har stöd för de functors som används:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

En anrops bara literal kan användas som ett värde, t. ex. tilldela en variabel eller skicka till ett annat anrop.
I det här fallet, om anropet har typ parametrar, måste de anges som en del av det anropade värdet.
Ett anrops bara värde kan inte ha ospecificerade typ parametrar.

Om `Fun` till exempel är en funktion med signatur `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Anrops anrops anrops uttryck

Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.
Typen av anrops uttryck är utdatatypen för den anropande signaturen.

Om `Op` till exempel är en åtgärd med signatur `((Int, Qubit) => Double)`, är `Op(3, qubit1)` ett uttryck av typen `Double`.
På samma sätt är `Sin(0.1)` ett uttryck av typen `Double`om `Sin` är en funktion med signatur `(Double -> Double)`.
Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))`, är `Builder(3)` en funktion från till int.

Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.
För att anropa resultatet av att anropa `Builder` från föregående stycke är därför rätt syntax:

```qsharp
(Builder(3))(2)
```

När du anropar en typ-parameter som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.
Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.
Det krävs för partiellt program (se nedan) om ett argument av typen-parameter lämnas ospecificerat.
Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.

Om `Func` till exempel har signatur `('T1, 'T2, 'T1) -> 'T2`, `Op1` och `Op2` ha signatur `(Qubit[] => Unit is Adj)`, och `Op3` har signatur `(Qubit[] => Unit)`, för att anropa `Func` med `Op1` som det första argumentet `Op2` som det andra och `Op3` som tredje:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.

### <a name="partial-application"></a>Partiellt program

Med ett anrops bara uttryck kan ett nytt anropas genom att tillhandahålla en delmängd av argumenten för anropet.
Detta kallas _delvis program_.

I Q # uttrycks en delvis tillämpad anrops begränsning genom att ett normalt anrops uttryck skrivs, men med ett under streck `_`för de ospecificerade argumenten.
Det resulterande anropet har samma resultat typ som bas anropet och samma specialisering för åtgärder.
Indatatypen för det partiella programmet är helt enkelt den ursprungliga typen med de angivna argumenten borttagna.

Om en föränderligt-variabel skickas som ett angivet argument när du skapar ett partiellt program, används det aktuella värdet för variabeln.
Att ändra värdet för variabeln efteråt påverkar inte den partiella applikationen.

Om `Op` exempelvis har typen `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` har en typ `(((Qubit,Qubit), Double) => Unit is Adj)`, och därför har `Op(5,_)`.
- `Op(_,(_,1.0))` har typen `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))` har typen `((Int,Double) => Unit is Adj)`.
   Observera att vi har använt singleton tuple-motsvarighet här.

Om det delvis använda anropet har typ parametrar som inte kan härledas av kompilatorn, måste de tillhandahållas på anrops platsen.
Det partiella programmet kan inte ha några ospecificerade typ parametrar.

Om `Op` exempelvis har typen `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Rekursion

Q # callables kan vara direkt eller indirekt rekursivt.
Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.

Det finns två viktiga kommentarer om användningen av rekursion, men:

- Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.
  Detta kan ha en betydande inverkan på körnings tiden för algoritmen.
- Vid körning på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.
  I synnerhet identifierar inte Q #-kompilatorn och körnings miljön och optimerar slut rekursion.

## <a name="tuple-expressions"></a>Tuple-uttryck

En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges av `(` och `)`.
Till exempel är `(1, One)` ett `(Int, Result)` uttryck.

Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.

## <a name="user-defined-type-expressions"></a>Användardefinierade typ uttryck

En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.
Om `IntPair` exempelvis är en användardefinierad typ som baseras på `(Int, Int)`, är `IntPair(2,3)` en giltig litteral av den typen.

Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.

## <a name="unwrap-expressions"></a>Packa upp uttryck

I Q # är unwrap-operatorn ett avslutande utrops tecken `!`.
Om `IntPair` till exempel är en användardefinierad typ med underliggande typ `(Int, Int)`och `s` var en variabel med värde `IntPair(2,3)`, är `s!` `(2,3)`.

För användardefinierade typer definieras i termer av andra användardefinierade typer. den avbrytande operatorn kan upprepas. `s!!` anger till exempel det dubblerade omslutna värdet för `s`.
Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair`och `t` är en variabel med värde `WrappedPair(IntPair(1,2))`, är `t!!` `(1,2)`.

`!` operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.
`!` och `[]` binda positions läge; det vill säga `a[i]![3]` bör läsas som `((a[i])!)[3]`: ta `i`i `a`, packa upp den och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).

Prioriteten hos `!` operatören har en effekt som kanske inte är uppenbar.
Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.
Exempel:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Mat ris uttryck

En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som omges av `[` och `]`.
Alla element måste vara kompatibla med samma typ.

Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.
Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.
Till exempel, om `Op1`, `Op2`och `Op3` alla är `Qubit[] => Unit`, men `Op1` har stöd för `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:

- `[Op1, Op2]` är en matris med `(Qubit[] => Unit)` åtgärder.
- `[Op1, Op3]` är en matris med `(Qubit[] => Unit is Adj)` åtgärder.
- `[Op2, Op3]` är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.

Tomma mat ris strängar, `[]`, tillåts inte.
I stället med `new ★[0]`, där `★` är plats hållare för en lämplig typ, kan du skapa den önskade matrisen med längden noll.

Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.
`[1,2,3] + [4,5,6]` till exempel `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Skapa matris

Med en typ och ett `Int` uttryck kan `new` operatören användas för att allokera en ny matris med den aktuella storleken.
`new Int[i+1]` skulle till exempel allokera en ny `Int` matris med `i+1` element.

Elementen i en ny matris initieras till ett typ beroende standardvärde.
I de flesta fall är detta en variation på noll.

Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.
Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.
Detta liknar en null-referens i språk som C# eller Java.
Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt. Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays>.

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
 `Range` | Det tomma intervallet `1..1..0`
 `Callable` | _Ogiltigt anrops bara_
 `Array['T]` | `'T[0]`

Tuple-typer är initierade element-by-element.


### <a name="jagged-arrays"></a>Ojämna matriser

En taggad matris, som ibland kallas matriser, är en matris vars element är matriser. Elementen i en taggad matris kan ha olika storlekar. I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.

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


### <a name="array-slices"></a>Mat ris segment

Med ett mat ris uttryck och ett `Range` uttryck kan ett nytt uttryck skapas med hjälp av operatorn `[` och `]` matris.
Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen i `Range`, i den ordning som definieras av `Range`.
Om `a` till exempel är kopplat till en matris med `Double`s, är `a[3..-1..0]` ett `Double[]`-uttryck som innehåller de fyra första elementen i `a`, men i omvänd ordning som de visas i `a`.

Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.

Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att kunna segmentera.
Om till exempel `a` och `b` båda matriserna för `Int`s, uttrycks en sektor från sammanfogningen som:

```qsharp
(a+b)[1..2..7]
```

Alla matriser i Q # är noll-baserade.
Det vill säga det första elementet i en matris `a` alltid `a[0]`.

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

## <a name="array-element-expressions"></a>Uttryck för mat ris element

Med ett mat ris uttryck och ett `Int` uttryck kan ett nytt uttryck skapas med hjälp av operatorn `[` och `]` mat ris element.
Det nya uttrycket är av samma typ som matrisens element typ.
Om `a` till exempel är kopplat till en matris med `Double`s är `a[4]` ett `Double`-uttryck.

Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.
Om till exempel `a` och `b` båda matriserna för `Int`s, uttrycks ett element från sammanfogningen som:

```qsharp
(a+b)[13]
```

Alla matriser i Q # är noll-baserade.
Det vill säga det första elementet i en matris `a` alltid `a[0]`.


## <a name="copy-and-update-expressions"></a>Kopiera och uppdatera uttryck

Nya matriser kan skapas från befintliga med hjälp av kopierings-och-uppdatera-uttryck.
Ett kopierings-och-uppdatering-uttryck är ett uttryck i formuläret `expression1 w/ expression2 <- expression3`, där `expression1` måste vara av typen `T[]` för viss typ `T`. Den andra `expression2` definierar indexen för elementen som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen `Range`. Om `expression2` är av typen `Int`måste `expression3` vara av typen `T`. Om `expression2` är av typen `Range`måste `expression3` vara av typen `T[]`.

Ett kopierings-och-uppdatera-uttryck `arr w/ idx <- value` skapar en ny matris med alla element som anges till motsvarande-element i `arr`, förutom elementen på `idx`, som är inställda på en/ett (a) `value`. Om `arr` till exempel innehåller en matris `[0,1,2,3]` 
- `arr w/ 0 <- 10` är matrisen `[10,1,2,3]`.
- `arr w/ 2 <- 10` är matrisen `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` är matrisen `[10,1,12,3]`.

Det finns liknande uttryck för namngivna objekt i användardefinierade typer. Överväg till exempel typen 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Om `c` innehåller värdet av typen `Complex(1.,-1.)`, är `c w/ Re <- 0.` ett uttryck av typen `Complex` som utvärderas till `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Villkors uttryck

Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|`.
`a==b ? c | d`till exempel.
I det här exemplet kommer värdet för villkors uttrycket att `c` om `a==b` är sant och `d` om det är falskt.

De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.
I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.
Till exempel, om `Op1`, `Op2`och `Op3` alla är `Qubit[]=>Unit`, men `Op1` har stöd för `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:

- `flag ? Op1 | Op2` är en `(Qubit[] => Unit)` åtgärd.
- `flag ? Op1 | Op3` är en `(Qubit[] => Unit is Adj)` åtgärd.
- `flag ? Op2 | Op3` är en `(Qubit[] => Unit is Ctl)` åtgärd.

Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.
Om `a==b` till exempel är sant, i fallet `a==b ? C(qs) | D(qs)`, om är sant, anropas `C`-åtgärden och om den är false anropas bara `D`.
Detta liknar korta kretsar på andra språk.


## <a name="operator-precedence"></a>Prioritet för Operator

Alla binära operatorer är rätt associerade, förutom för `^`.

Hakparenteser, `[` och `]`, för matris-och indexering av matriser, bind före valfri operator.

Functors-`Adjoint` och `Controlled`-bindning efter mat ris indexering men före alla andra operatorer.

Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.

Operatorer i prioritetsordning, från högsta till lägsta:

Operator | Ariteten | Beskrivning | Operands typer
---------|----------|---------|---------------
 efterföljande `!` | Operator | Packa upp | Valfri användardefinierad typ
 `-`, `~~~`, `not` | Operator | Numeriskt negativ, bitvis komplement, logisk negation | `Int`, `BigInt` eller `Double` för `-`, `Int` eller `BigInt` för `~~~`, `Bool` för `not`
 `^` | binär | Heltals effekt | `Int` eller `BigInt` för basen `Int` för exponenten
 `/`, `*`, `%` | binär | Division, multiplikation, heltals-modulus | `Int`, `BigInt` eller `Double` för `/` och `*`, `Int` eller `BigInt` för `%`
 `+`, `-` | binär | Kombination av addition eller sträng och matris, subtraktion | `Int`, `BigInt` eller `Double`, även `String` eller valfri mat ris typ för `+`
 `<<<`, `>>>` | binär | Vänster SKIFT, höger Skift | `Int` eller `BigInt`
 `<`, `<=`, `>`, `>=` | binär | Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser | `Int`, `BigInt` eller `Double`
 `==`, `!=` | binär | lika med, inte lika med jämförelser | vilken primitiv typ som helst
 `&&&` | binär | Bitvis och | `Int` eller `BigInt`
 `^^^` | binär | Bitvis XOR | `Int` eller `BigInt`
 <code>\|\|\|</code> | binär | Bitvis eller | `Int` eller `BigInt`
 `and` | binär | Logiska och | `Bool`
 `or` | binär | Logiska eller | `Bool`
 `..` | Binär/ternär | Intervall operator | `Int`
 `?` `|` | Ternär | Villkorsstyrd | `Bool` för den vänstra sidan
`w/` `<-` | Ternär | Kopiera och uppdatera | Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)