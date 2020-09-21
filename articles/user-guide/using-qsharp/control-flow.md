---
title: Kontroll flöde i Q#
description: Slingor, villkor osv.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8c873868d6f697fc90b23a38c11f35e46b40c4f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759670"
---
# <a name="control-flow-in-no-locq"></a>Kontroll flöde i Q#

I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som andra vanliga tvingande klassiska språk.
Du kan dock ändra kontroll flödet på tre olika sätt:

* `if` instruktioner
* `for` slingor
* `repeat-until-success` slingor

`if` `for` Konstruktionerna för och kontroll flödet fortsätter att vara bekanta med de flesta klassiska programmeringsspråk. [`Repeat-until-success`](#repeat-until-success-loop) slingor beskrivs längre fram i den här artikeln.

Det är viktigt `for` att du använder slingor och `if` uttryck i åtgärder för vilka [specialisering](xref:microsoft.quantum.guide.operationsfunctions) genereras automatiskt. I det scenariot kastar det intilliggande av en `for` slinga riktningen och tar det angränsande av varje iteration.
Den här åtgärden följer principen "skor-och-SOCKS": om du vill ångra att sätta igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS. 

## <a name="if-else-if-else"></a>Om, annars, annars

`if`Instruktionen stöder villkorlig körning.
Det består av nyckelordet `if` , ett booleskt uttryck inom parentes och ett instruktions block ( _then_ -blocket).
Valfritt antal Else-If-satser kan följa, var och en består av nyckelordet `elif` , ett booleskt uttryck inom parentes och ett instruktions block ( _Else-If-_ block).
Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).

`if`Villkoret utvärderas och om det är *Sant*körs blocket. *then*
Om villkoret är *falskt*utvärderas det första Else-If-villkoret. om detta är sant körs *Else-If-* blocket.
Annars utvärderar det andra-IF-blocket och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.
Om det ursprungliga *IF* -villkoret och alla Else-If-satserna evalueras till *false*körs *Else* -blocket om det anges.

Observera att det körs på det egna omfånget.
Bindningar som görs inuti ett `if` , `elif` eller- `else` block visas inte när blocket slutar.

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

## <a name="for-loop"></a>For-loop

`for`Instruktionen stöder iteration över ett heltals intervall eller en matris.
Instruktionen består av nyckelordet `for` följt av en symbol-eller symbol-tupel, nyckelordet `in` och ett uttryck av typen `Range` eller matris, allt inom parentes och ett instruktions block.

Instruktions blocket (bröd texten i slingan) körs flera gånger, med den definierade symbolen (loop-variabeln) kopplad till varje värde i intervallet eller matrisen.
Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.
Uttrycket utvärderas fullständigt innan loopen inleds, och ändras inte när loopen körs.

Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.
Loop-variabeln är inte kopplad efter att for-slingan har slutförts.
Bindningen för sling-variabeln är oföränderlig och följer samma regler som andra variabel bindningar. 

I de här exemplen `qubits` är ett register över qubits (t. ex. typ `Qubit[]` ). 

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

Observera att vi i slutet använder den aritmetiska operatorn Shift-vänstra binära operatorn `<<<` . Mer information finns i [numeriska uttryck](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Upprepa-tills-lyckad-slinga

Q#Språket tillåter att klassiskt kontroll flöde är beroende av resultatet av att mäta qubits.
Med den här funktionen aktive ras implementera kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.
Exempel på detta är ru: er-mönster ( *REPEAT-until-lyckat* ) i Q# .
Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar. kostnaden beror på den faktiska körningen och Interfoliering av flera möjliga grenar.

För att under lätta upprepade tills klart (ru: er) mönster, Q# stöder konstruktioner

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
Om villkoret är sant slutförs instruktionen. annars körs korrigeringen och instruktionen körs igen, från och med loop-texten.

Alla tre delar av en ru: er-slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång *för varje upprepning*, så symboler som är kopplade till innehållet är tillgängliga i både testet och korrigeringen.
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

Fler exempel och mer information finns i [Upprepa-till-Slutför-exempel](#repeat-until-success-examples) i den här artikeln.

> [!TIP]   
> Undvik att använda repetitions-till-Slutför-slingor inuti functions. Använd *while* -slingor för att tillhandahålla motsvarande funktioner i functions. 

## <a name="while-loop"></a>While-loop

Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation. De används ofta i vissa klasser av Quantum-algoritmer – därför den dedikerade språk konstruktionen i Q# . Loopar som bryts baserat på ett villkor och vars körnings längd är således okänd vid kompileringen, hanteras dock med särskild försiktighet i en Quantum-körning. Användningen i functions är dock inte problematisk eftersom dessa slingor bara innehåller kod som körs på konventionell (icke-Quantum) maskin vara. 

Q#stöder därför endast användningen av while-slingor i functions. En `while` instruktion består av nyckelordet `while` , ett booleskt uttryck inom parentes och ett instruktions block.
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

Exempel:
```qsharp
return 1;
```
eller
```qsharp
return (results, qubits);
```

* Ett anrop som returnerar en tom tupel, `()` kräver ingen Return-instruktion.
* Om du vill ange en tidig utträde från åtgärden eller funktionen använder du `return ();` .
Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.
* Det finns inget maximalt antal retur uttryck i en åtgärd.
Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.

   
## <a name="fail-statement"></a>Instruktionen misslyckande

Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.
Det består av nyckelordet `fail` följt av en sträng och ett avslutande semikolon.
Instruktionen returnerar strängen till den klassiska driv rutinen som fel meddelande.

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

I ett vanligt användnings fall Q# implementerar följande åtgärd en rotation runt en onormal axel om $ (i + 2i Z)/\sqrt {5} $ på Bloch-sfären. Implementeringen använder ett känt ru: er-mönster:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>RU: er-slinga med en föränderligt-variabel i omfånget

I det här exemplet visas användningen av en föränderligt-variabel, `finished` som ligger inom omfånget för hela upprepnings-tills-korrigering-loopen och som initieras före loopen och uppdateras i korrigerings steget.

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

### <a name="rus-without-fixup"></a>RU: er utan `fixup`

I det här exemplet visas en ru: er-slinga utan korrigerings steget. Koden är en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ med hjälp av `H` och- `T` grindarna.
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

Slutligen är det ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, med början från $ \ket{+} $ State.

Viktiga programmerings funktioner som visas i den här åtgärden är:

* En mer komplex `fixup` del av slingan, som inbegriper Quantum-åtgärder. 
* Användning av `AssertMeasurementProbability` instruktioner för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.

Mer information om [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) -och-åtgärder finns i [testa och felsöka](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

Mer information finns i avsnittet [om enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Nästa steg

Lär dig mer om att [testa och felsöka](xref:microsoft.quantum.guide.testingdebugging) i Q# .
