---
title: 'Q # uttryck'
description: 'Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683930"
---
# <a name="expressions"></a>Uttryck

## <a name="grouping"></a>Baserat

Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.
`(7)` `Int` Är till exempel ett uttryck, `([1,2,3])` är ett uttryck av typen matris för `Int`s och `((1,2))` är ett uttryck med typen. `(Int, Int)`

Motsvarigheten mellan enkla värden och tupler med ett enda element som beskrivs i [typ modellen](xref:microsoft.quantum.language.type-model#tuple-types) tar bort tvetydigheten `(6)` mellan som en grupp `(6)` och som en tupel med ett enda element.

## <a name="symbols"></a>Symboler

Namnet på en symbol som är kopplad till ett värde av typen `'T` är ett uttryck av typen. `'T`
Om symbolen `count` till exempel är kopplad till heltal svärdet `5` `count` är ett heltals uttryck.

## <a name="numeric-expressions"></a>Numeriska uttryck

Numeriska uttryck är uttryck av typen `Int`, `BigInt`eller `Double`.
Det vill säga att de är antingen heltals-eller flytt ALS nummer.

`Int`litteraler i Q # är identiska med heltals strängar i C#, förutom att ingen efterföljande "l" eller "L" krävs (eller tillåts).
Hexadecimala och binära heltal stöds med prefixet "0x" och "0b".

`BigInt`litteraler i Q # är identiska med Big heltals strängar i .NET, med ett efterföljande "l" eller "L".
Hexadecimala Big heltal stöds med ett "0x"-prefix.
Det innebär att följande är giltig användning av `BigInt` litteraler:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`litteraler i Q # är identiska med dubbel litteraler i C#, förutom att ingen efterföljande "d" eller "D" krävs (eller tillåts).

Med ett mat ris uttryck för valfri element typ kan `Int` ett uttryck skapas med hjälp av `Length` den inbyggda funktionen, med mat ris uttrycket omslutna i parentes `(` och. `)`
Om `a` till exempel är kopplat till en matris, `Length(a)` är ett heltals uttryck.
Om `b` är `Int[][]`en matris med heltals `Length(b)` matriser, är antalet underordnade matriser i `b`och `Length(b[1])` är antalet heltal i den andra under matrisen i. `b`

Två numeriska uttryck av samma typ, de binära operatorerna `+`, `-`, `*`och `/` kan användas för att skapa ett nytt numeriskt uttryck.
Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.

Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.
På samma sätt `^` kan användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.
Slutligen `^` kan du använda ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.
I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.

Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big- `%` heltals uttryck skapas `&&&` med operatörerna (Modulus `|||` ), (BITVIS and) `^^^` , (bitvis or) eller (Bitvis XOR).

Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till `<<<` höger, kan operatorerna ( `>>>` aritmetisk vänster Shift) eller (aritmetiska höger Shift) användas för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.

Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.
Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.
Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet `mod 64`. det vill säga en skift på 1 och en förskjutning på 65 har samma resultat.

För både heltals-och Big heltals värden är skiften aritmetiska.
Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.
Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.

Heltals Division och heltals-Modulus följer samma beteende för negativa tal som C#.
Det `a % b` vill säga har alltid samma signera som `a`och `b * (a / b) + a % b` är alltid lika med. `a`
Ett exempel:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Big Integer-Division och Modulus fungerar på samma sätt.

Ett nytt uttryck kan skapas med hjälp av ett numeriskt uttryck med `-` hjälp av den unära operatorn.
Det nya uttrycket är av samma typ som komponent uttrycket.

Med alla heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med `~~~` den unära operatorn (bitvis komplement).

## <a name="boolean-expressions"></a>Booleska uttryck

De två `Bool` literala värdena `true` är `false`och.

Om du har två uttryck av samma primitiva typ kan `==` de `!=` och binära operatorerna användas för att `Bool` skapa ett uttryck.
Uttrycket är sant om de två uttrycken är lika och falskt om inte.

Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras. Du kan till exempel använda operatorn `!` "unwrap" (förklaras på sidan för [Q # typ modell](xref:microsoft.quantum.language.type-model#user-defined-types)).

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Likhets jämförelse `Qubit` för värden är identitets likhet; det vill säga om de två uttrycken identifierar samma qubit.
Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.

Jämförelse av `Double` värden kan vara missvisande på grund av avrundnings effekter.
Till exempel `49.0 * (1.0/49.0) != 1.0`.

Två numeriska uttryck, de binära operatorerna `>` `<` `>=`,, och `<=` kan användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.

Med två booleska uttryck kan de `and` och `or` binära operatorerna användas för att skapa ett nytt booleskt uttryck som är sant om båda uttrycken (ansvars båda eller båda) är sanna.

Med alla booleska uttryck kan den `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.

## <a name="string-expressions"></a>Sträng uttryck

Q # tillåter att strängar används i `fail` instruktionen och `Log` standard funktionen.

Strängar i Q # är antingen litteraler eller interpolerade strängar.
Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode- `"`tecken som omges av dubbla citat tecken.
I `\` en sträng kan back snedstrecket användas för att undvika ett dubbelt citat tecken och för att infoga en ny rad `\n`som, en vagn retur som `\r`och en flik som. `\t`
Till exempel:

```qsharp
"\"Hello world!\", she said.\n"
```

Q #-syntaxen för String-interpolation är en delmängd av C# 7,0-syntaxen. Q # stöder inte orda Grant (multi-line) interpolerade strängar.
Se [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) för C#-syntaxen.

Uttryck i en interpolerad sträng följer Q # syntax, inte C#-syntax.
Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.

## <a name="qubit-expressions"></a>Qubit-uttryck

De enda `Qubit` uttrycken är symboler som är `Qubit` kopplade till värden eller mat `Qubit` ris element.
Det finns inga `Qubit` litteraler.

## <a name="pauli-expressions"></a>Pauli-uttryck

De fyra `Pauli` värdena, `PauliI`, `PauliX`, `PauliY`och `PauliZ`, är giltiga `Pauli` uttryck.

Förutom så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element `Pauli` .

## <a name="result-expressions"></a>Resultat uttryck

De två `Result` värdena `One` och `Zero`, är giltiga `Result` uttryck.

Förutom så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element `Result` .
Observera särskilt att `One` inte är detsamma som heltalet `1`och det finns ingen direkt konvertering mellan dem.
Samma sak gäller `Zero` och `0`.

## <a name="range-expressions"></a>Intervall uttryck

Alla `Int` tre uttryck `start`, `step`, och `stop`, `start .. step .. stop` är ett intervall uttryck vars första element är `start`, det andra elementet är `start+step`, det tredje elementet `start+step+step`, osv., tills `stop` det skickas.
Ett intervall kan vara tomt om, t. ex `step` . är positivt `stop < start`och.
Det sista elementet `stop` i intervallet är om skillnaden mellan `start` och `stop` är en integral multipel av; `step` det vill säga att intervallet inkluderas i båda ändar.

Två `Int` uttryck `start` har angetts och `stop` `start .. stop` är ett intervall uttryck som är lika med `start .. 1 .. stop`.
Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start`; i sådana fall är intervallet tomt.

Några exempel intervall är:

- `1..3`är intervallet 1, 2, 3.
- `2..2..5`är intervallet 2, 4.
- `2..2..6`är intervallet 2, 4, 6.
- `6..-2..2`är intervallet 6, 4, 2.
- `2..1`är det tomma intervallet.
- `2..6..7`är intervallet 2.
- `2..2..1`är det tomma intervallet.
- `1..-1..2`är det tomma intervallet.

## <a name="callable-expressions"></a>Anrops bara uttryck

En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.
`X` Är till exempel en åtgärds-literal som refererar till standard biblioteks `X` åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.

Om en åtgärd har stöd `Adjoint` för Functor `Adjoint op` är ett åtgärds uttryck.
På samma sätt `Controlled op` är det ett åtgärds `Controlled` uttryck om åtgärden stöder Functor.
Typerna av dessa uttryck anges i [Functors](xref:microsoft.quantum.language.type-model#functors).

Functors (`Adjoint` och `Controlled`) binder mer nära varandra än alla andra operatorer, förutom unwrap- `!` operatorn och mat ris `[]`indexering med.
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

Om `Fun` är till exempel en funktion med signatur `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Anrops anrops anrops uttryck

Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.
Typen av anrops uttryck är utdatatypen för den anropande signaturen.

Om `Op` är till exempel en åtgärd med signatur `((Int, Qubit) => Double)`, `Op(3, qubit1)` är ett uttryck av typen. `Double`
På samma sätt, `Sin` om är en funktion med `(Double -> Double)`signatur `Sin(0.1)` , är ett uttryck av `Double`typen.
Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))`, `Builder(3)` är en funktion från till int.

Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.
För att anropa resultatet av anrop `Builder` från föregående stycke är därför rätt syntax:

```qsharp
(Builder(3))(2)
```

När du anropar en typ-parameter som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.
Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.
Det krävs för partiellt program (se nedan) om ett argument av typen-parameter lämnas ospecificerat.
Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.

Om `Func` har exempelvis signatur `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)`och har signatur, och `Op3` har signatur `(Qubit[] => Unit)`, för att anropa `Func` med `Op1` som första argument, `Op2` som den andra, och `Op3` som tredje:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.

### <a name="partial-application"></a>Partiellt program

Med ett anrops bara uttryck kan ett nytt anropas genom att tillhandahålla en delmängd av argumenten för anropet.
Detta kallas _delvis program_.

I Q # uttrycks en delvis Använd anrops begränsning genom att skriva ett normalt anrops uttryck, men med ett under `_`streck, för de ospecificerade argumenten.
Det resulterande anropet har samma resultat typ som bas anropet och samma specialisering för åtgärder.
Indatatypen för det partiella programmet är helt enkelt den ursprungliga typen med de angivna argumenten borttagna.

Om en föränderligt-variabel skickas som ett angivet argument när du skapar ett partiellt program, används det aktuella värdet för variabeln.
Att ändra värdet för variabeln efteråt påverkar inte den partiella applikationen.

Till exempel om `Op` har typen `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))`har typen `(((Qubit,Qubit), Double) => Unit is Adj)`, och därför har `Op(5,_)`.
- `Op(_,(_,1.0))`har typen `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))`har typen `((Int,Double) => Unit is Adj)`.
   Observera att vi har använt singleton tuple-motsvarighet här.

Om det delvis använda anropet har typ parametrar som inte kan härledas av kompilatorn, måste de tillhandahållas på anrops platsen.
Det partiella programmet kan inte ha några ospecificerade typ parametrar.

Till exempel om `Op` har typen `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

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

En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges `(` av `)`och.
`(1, One)` Är till exempel ett `(Int, Result)` uttryck.

Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.

## <a name="user-defined-type-expressions"></a>Användardefinierade typ uttryck

En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.
Om `IntPair` är till exempel en användardefinierad typ som baseras på `(Int, Int)`, `IntPair(2,3)` är en giltig litteral av den typen.

Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.

## <a name="unwrap-expressions"></a>Packa upp uttryck

I Q # är unwrap-operatorn ett avslutande utrops tecken `!`.
Om `IntPair` är till exempel en användardefinierad typ med underliggande typ `(Int, Int)`och `s` var en variabel med värde `IntPair(2,3)`, `s!` skulle det vara. `(2,3)`

För användardefinierade typer definieras i termer av andra användardefinierade typer. den avbrytande operatorn kan upprepas. `s!!` anger t. ex. dubblerat-värde för `s`.
Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair`och `t` är en variabel med värde `WrappedPair(IntPair(1,2))`, `t!!` blir det alltså. `(1,2)`

`!` Operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.
`!`och `[]` binda positions läge; det vill säga `a[i]![3]` bör se ut så `((a[i])!)[3]`här: ta `i`elementet "th" `a`, packa upp det och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).

Prioriteten hos `!` operatorn har en effekt som kanske inte är uppenbar.
Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.
Ett exempel:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Mat ris uttryck

En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som `[` omges av och `]`.
Alla element måste vara kompatibla med samma typ.

Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.
Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.
`Op1`Till exempel, `Op2`, och `Op3` alla `Qubit[] => Unit`, men `Op1` stöder `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:

- `[Op1, Op2]`är en matris med `(Qubit[] => Unit)` åtgärder.
- `[Op1, Op3]`är en matris med `(Qubit[] => Unit is Adj)` åtgärder.
- `[Op2, Op3]`är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.

Tomma mat ris strängar, `[]`tillåts inte.
I stället `new ★[0]`använda, `★` där är plats hållare för lämplig typ, kan du skapa den önskade matrisen med längden noll.

Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.
Till exempel `[1,2,3] + [4,5,6]` är `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Skapa matris

Med en typ och ett `Int` uttryck kan `new` operatorn användas för att allokera en ny matris med den aktuella storleken.
Allokera till exempel `new Int[i+1]` en ny `Int` matris med `i+1` element.

Elementen i en ny matris initieras till ett typ beroende standardvärde.
I de flesta fall är detta en variation på noll.

Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.
Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.
Detta liknar en null-referens i språk som C# eller Java.
Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt. Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays>.

Standardvärdena för varje typ är:

Typ | Standardvärde
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

Med ett mat ris uttryck och `Range` ett uttryck kan ett nytt uttryck skapas med operatorn `[` array `]` och array.
Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen `Range`i, i den ordning som definieras `Range`av.
Om `a` till exempel är kopplat till en matris `Double`med s, `a[3..-1..0]` är ett `Double[]` uttryck som innehåller de första fyra elementen i, `a` men i omvänd ordning som de visas i. `a`

Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.

Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att kunna segmentera.
Om `a` till exempel `b` är båda matriserna i `Int`s, uttrycks en sektor från sammanfogningen som:

```qsharp
(a+b)[1..2..7]
```

Alla matriser i Q # är noll-baserade.
Det vill säga det första elementet i en matris `a` är alltid `a[0]`.

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

Med ett mat ris uttryck och `Int` ett uttryck kan ett nytt uttryck skapas med operatorn `[` och `]` array element-operatorn.
Det nya uttrycket är av samma typ som matrisens element typ.
Om `a` till exempel är kopplat till en matris med `Double`s, `a[4]` är ett `Double` uttryck.

Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.
Om `a` och `b` är båda matriserna i `Int`s, uttrycks t. ex. ett element från sammanfogningen:

```qsharp
(a+b)[13]
```

Alla matriser i Q # är noll-baserade.
Det vill säga det första elementet i en matris `a` är alltid `a[0]`.


## <a name="copy-and-update-expressions"></a>Kopiera och uppdatera uttryck

Nya matriser kan skapas från befintliga med hjälp av kopierings-och-uppdatera-uttryck.
Ett kopierings-och-uppdatering-uttryck är ett uttryck för `expression1 w/ expression2 <- expression3`formuläret, `expression1` där måste vara av typen `T[]` av viss typ `T`. Den andra `expression2` definierar indexen för de element som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen. `Range` Om `expression2` är av typen `Int`måste `expression3` vara av typen `T`. Om `expression2` är av typen `Range`måste `expression3` vara av typen `T[]`.

Ett Copy-och-Update- `arr w/ idx <- value` uttryck skapar en ny matris med alla element som har angetts till motsvarande- `arr`element i, förutom elementen på `idx`, som är inställda på en/ett i. `value` Om `arr` t. ex. innehåller en `[0,1,2,3]`matris, 
- `arr w/ 0 <- 10`är matrisen `[10,1,2,3]`.
- `arr w/ 2 <- 10`är matrisen `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]`är matrisen `[10,1,12,3]`.

Det finns liknande uttryck för namngivna objekt i användardefinierade typer. Överväg till exempel typen 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Om `c` innehåller `Complex(1.,-1.)`värdet av typen `c w/ Re <- 0.` är det ett uttryck av typen `Complex` som utvärderas till. `Complex(0.,-1.)`

## <a name="conditional-expressions"></a>Villkors uttryck

Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|`.
Till exempel `a==b ? c | d`.
I det här exemplet är värdet för villkors uttrycket `c` IF `a==b` sant och `d` om det är falskt.

De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.
I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.
`Op1`Till exempel, `Op2`, och `Op3` alla `Qubit[]=>Unit`, men `Op1` stöder `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:

- `flag ? Op1 | Op2`är en `(Qubit[] => Unit)` åtgärd.
- `flag ? Op1 | Op3`är en `(Qubit[] => Unit is Adj)` åtgärd.
- `flag ? Op2 | Op3`är en `(Qubit[] => Unit is Ctl)` åtgärd.

Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.
Om är `a==b ? C(qs) | D(qs)`till exempel, om `a==b` är sant, kommer `C` åtgärden att anropas och om den är false anropas bara. `D`
Detta liknar korta kretsar på andra språk.


## <a name="operator-precedence"></a>Prioritet för Operator

Alla binära operatorer är rätt associerade, förutom för `^`.

Hakparenteser `[` och `]`, för mat ris segmentering och indexering, bind före valfri operator.

Functors `Adjoint` och `Controlled` bind efter mat ris indexering, men före alla andra operatorer.

Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.

Operatorer i prioritetsordning, från högsta till lägsta:

Operator | Ariteten | Beskrivning | Operands typer
---------|----------|---------|---------------
 avslutande`!` | Operator | Packa upp | Valfri användardefinierad typ
 `-`, `~~~`, `not` | Operator | Numeriskt negativ, bitvis komplement, logisk negation | `Int`, `BigInt` eller `Double` för `-`, `Int` eller `BigInt` `~~~`för `Bool``not`
 `^` | Binär | Heltals effekt | `Int`eller `BigInt` för basen `Int` för exponenten
 `/`, `*`, `%` | Binär | Division, multiplikation, heltals-modulus | `Int`, `BigInt` eller `Double` för `/` och `*`, `Int` eller `BigInt` för`%`
 `+`, `-` | Binär | Kombination av addition eller sträng och matris, subtraktion | `Int``BigInt` eller `Double`, även `String` eller valfri mat ris typ för`+`
 `<<<`, `>>>` | Binär | Vänster SKIFT, höger Skift | `Int` eller `BigInt`
 `<`, `<=`, `>`, `>=` | Binär | Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser | `Int``BigInt` eller`Double`
 `==`, `!=` | Binär | lika med, inte lika med jämförelser | vilken primitiv typ som helst
 `&&&` | Binär | Bitvis och | `Int` eller `BigInt`
 `^^^` | Binär | Bitvis XOR | `Int` eller `BigInt`
 <code>\|\|\|</code> | Binär | Bitvis eller | `Int` eller `BigInt`
 `and` | Binär | Logiska och | `Bool`
 `or` | Binär | Logiska eller | `Bool`
 `..` | Binär/ternär | Intervall operator | `Int`
 `?` `|` | Ternär | Villkorsstyrd | `Bool`för den vänstra sidan
`w/` `<-` | Ternär | Kopiera och uppdatera | Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)
