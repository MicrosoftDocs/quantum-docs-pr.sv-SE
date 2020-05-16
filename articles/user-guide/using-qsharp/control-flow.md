---
title: 'Kontroll flöde i Q #'
description: Slingor, villkor osv.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430959"
---
# <a name="control-flow-in-q"></a>Kontroll flöde i Q #

I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som de flesta vanliga tvingande klassiska språk.
Det här kontroll flödet kan ändras, men på tre olika sätt:

- `if`instruktioner
- `for`slingor
- `repeat`-`until`slingor

Vi skjuter upp diskussionen om det [senare.](#repeat-until-success-loop)
`if` `for` Kontroll flödes-och kontroll flödes konstruktionerna går dock bra att känna till i de flesta klassiska programmeringsspråk.

`for`Det är viktigt att slingor och `if` uttryck även kan användas i åtgärder för vilka specialisering genereras automatiskt. I så fall kastar det intilliggande av en `for` slinga riktningen och tar det angränsande av varje iteration.
Det här följer principen "skor-och-SOCKS": om du vill ångra att du kommer igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS.
Det fungerar mindre bra om du vill prova och ta din SOCKS medan du fortfarande använder dina skor!

## <a name="if-else-if-else"></a>Om, annars, annars

`if`Instruktionen stöder villkorlig körning.
Det består av nyckelordet `if` , en öppen parentes `(` , ett booleskt uttryck, en avslutande parentes `)` och ett instruktions block ( _then_ -block).
Detta kan följas av valfri mängd Else-If-satser, som består av nyckelordet `elif` , en öppen parentes `(` , ett booleskt uttryck, en högerparentes `)` och ett instruktions block ( _Else-If-_ block).
Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).

`if`Villkoret utvärderas och om det är sant körs blocket.
Om villkoret är falskt utvärderas det första Else-If-villkoret. om det är sant körs det Else-If-blocket.
Annars testas det andra-IF-blocket, och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.
Om det ursprungliga IF-villkoret och alla Else-If-satser utvärderas till false körs Else-blocket om ett har angetts.

Observera att det körs på det egna omfånget.
Bindningar som görs inuti ett `if` , `elif` eller- `else` block visas inte efter dess slut.

Exempel:

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
eller
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>For-slinga

`for`Instruktionen stöder iteration över ett heltals intervall eller över en matris.
Instruktionen består av nyckelordet `for` , en öppen parentes `(` följt av en symbol-eller symbol-tupel, nyckelordet `in` , ett uttryck av typen `Range` eller matris, en högerparentes `)` och ett instruktions block.

Instruktions blocket (bröd texten i slingan) körs upprepade gånger, med de definierade symbolerna (loop-variabeln) som är kopplade till varje värde i intervallet eller matrisen.
Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.
Uttrycket utvärderas fullständigt innan det går in i loopen och ändras inte när slingan körs.

Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.
I synnerhet är loop-variabeln inte kopplad efter att for-slingan har slutförts.
Bindningen för de deklarerade symbolerna är oföränderlig och följer samma regler som andra variabel bindningar. 

I vissa exempel är supposing `qubits` ett register över qubits (t. ex. av typ `Qubit[]` ). 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
Observera att i slutet använder vi den aritmetiska operatorn Shift-vänstra, `<<<` och information om vilka som kan hittas på [numeriska uttryck](xref:microsoft.quantum.guide.expressions#numeric-expressions)


## <a name="repeat-until-success-loop"></a>Upprepa-tills-lyckad-slinga

Med hjälp av Q #-språket kan ett klassiskt kontroll flöde vara beroende av resultatet av att mäta qubits.
Den här funktionen aktiverar implementering av kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.
Som exempel är det enkelt att implementera så kallade ru: er-mönster ( *REPEAT-until-lyckades* ) i Q #.
Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar, men för vilka den faktiska kostnaden är beroende av en faktisk körning och en faktisk Interfoliering av olika möjliga grenar.

Q # stöder konstruktioner för att under lätta upprepningar av ru: er-mönster.

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

var `expression` är ett giltigt uttryck som utvärderas till ett värde av typen `Bool` .
Loop-texten körs och sedan utvärderas villkoret.
Om villkoret är sant slutförs instruktionen. annars utförs korrigeringen och instruktionen körs igen från och med loop-texten.

Alla tre delarna av en REPEAT/until-slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång *för varje upprepning*, så symboler som är kopplade till texten är tillgängliga i testet och i korrigeringen.
Att slutföra körningen av korrigeringen avslutar dock omfånget för instruktionen, så att symbol bindningar som görs under bröd texten eller korrigeringen inte är tillgängliga i efterföljande upprepningar.

Vidare `fixup` är uttrycket ofta användbart men inte alltid nödvändigt.
I fall där det inte behövs, konstruktionen
```qsharp
repeat {
    // do stuff
}
until (expression);
```
är också ett giltigt ru: er-mönster.

Längst ned på sidan presenteras några [exempel på ru: er-slingor](#repeat-until-success-examples).

> [!TIP]   
> Undvik att använda repetitions-till-Slutför-slingor inuti functions. Motsvarande funktioner tillhandahålls av while-slingor i functions. 

## <a name="while-loop"></a>While-slinga

Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation. De används ofta i vissa klasser av Quantum-algoritmer – därför är den dedikerade språk konstruktionen i Q #. Loopar som bryts baserat på ett villkor och vars körnings längd alltså är okänd vid kompileringen måste dock hanteras med särskild försiktighet i en Quantum-körning. Deras användning i functions å andra sidan är problematisk, eftersom dessa endast innehåller kod som ska köras på konventionell (icke-Quantum) maskin vara. 

Q # stöder därför endast användningen av while-slingor i functions. En `while` instruktion består av nyckelordet `while` , en öppen parentes `(` , ett villkor (t. ex. ett booleskt uttryck), en avslutande parentes `)` och ett instruktions block.
Instruktions blocket (bröd texten i slingan) körs så länge villkoret utvärderas till `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return-instruktion

Return-instruktionen avslutar körningen av en åtgärd eller funktion och returnerar ett värde till anroparen.
Det består av nyckelordet `return` följt av ett uttryck av lämplig typ och ett avslutande semikolon.

Ett anrop som returnerar en tom tupel, `()` kräver ingen Return-instruktion.
Om en tidig avslutning önskas, `return ()` kan användas i det här fallet.
Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.

Det finns inget maximalt antal retur uttryck i en åtgärd.
Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.

Exempel:
```qsharp
return 1;
```
eller
```qsharp
return ();
```
eller
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Instruktionen misslyckande

Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.
Det består av nyckelordet `fail` följt av en sträng och ett avslutande semikolon.
Strängen returneras till den klassiska driv rutinen som fel meddelande.

Det finns ingen begränsning för antalet misslyckande uttryck i en åtgärd.
Kompilatorn kan generera en varning om instruktioner följer en felaktig instruktion i ett block.

Exempel:
```qsharp
fail $"Impossible state reached";
```
eller, med hjälp av [interpolerade strängar](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Upprepa-till-Slutför-exempel

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>RU: er-mönster för en qubit rotation om en onormal axel 

I ett vanligt användnings fall implementerar följande Q #-åtgärd en rotation runt en onormal axel om $ (I + 2i Z)/\sqrt {5} $ på Bloch-sfären. Detta åstadkoms med hjälp av ett känt ru: er-mönster:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a>RU: er-slinga med föränderligt-variabel i omfånget

Det här exemplet visar användningen av en föränderligt-variabel `finished` som ligger inom omfånget för hela upprepnings-till-korrigering-loopen och som initieras före loopen och uppdateras i korrigerings steget.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>RU: er utan`fixup`

Följande kod är till exempel en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ med hjälp av- `H` och- `T` grindarna.
Slingan slutar i $ \frac {8} {5} $-upprepningar i genomsnitt.
Se [*REPEAT-until-lyckades: icke-deterministisk dekomposition av Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick och Svore, 2014) för mer information.

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>RU: er för att förbereda ett Quantum-tillstånd

Slutligen visar vi ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, med början från $ \ket{+} $ State.
Se även [exempel på enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Viktiga programmerings funktioner som visas i den här åtgärden är en mer komplex `fixup` del av slingan, vilket inbegriper Quantum-åtgärder och användningen av- `AssertProb` instruktioner för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.
Se även [testning och fel sökning](xref:microsoft.quantum.guide.testingdebugging) för mer information om- [`Assert`](xref:microsoft.quantum.intrinsic.assert) och- [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) åtgärder.


## <a name="whats-next"></a>Vad står på tur?
Lär dig mer om [testning och fel sökning](xref:microsoft.quantum.guide.testingdebugging) i Q #.