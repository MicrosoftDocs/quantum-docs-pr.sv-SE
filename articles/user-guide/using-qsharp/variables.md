---
title: 'Variabler i Q #'
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430908"
---
# <a name="variables-in-q"></a>Variabler i Q #

Q # skiljer sig mellan föränderligt och oföränderliga symboler, eller "variabler", som är kopplade/tilldelade till uttryck.
I allmänhet uppmuntras användningen av oföränderliga symboler eftersom den tillåter kompilatorn att utföra mer optimeringar.

Den vänstra sidan av en bindning består av en symbol tupel och den högra sidan av ett uttryck.

## <a name="immutable-variables"></a>Variabler som inte är oföränderlig

Ett värde av valfri typ i Q # kan tilldelas en variabel för åter användning i en åtgärd eller funktion med hjälp av `let` nyckelordet.

En oföränderlig bindning består av nyckelordet `let` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda symbolerna till och ett avslutande semikolon.

Till exempel:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Detta tilldelar en viss matris av Pauli-operatörer till variabel namnet (eller symbol) `measurementOperator` .

> [!NOTE]
> Vi behöver inte uttryckligen ange typen av vår nya variabel, eftersom uttrycket till höger i `let` instruktionen är entydigt och typen härleds av kompilatorn. 

Variabler som definieras med `let` är *oföränderliga*, vilket innebär att när det har definierats kan det inte längre ändras på något sätt.
Detta möjliggör flera betalnings optimeringar, inklusive optimering av den klassiska logiken i variabler för att sorteras om för att tillämpa `Adjoint` en åtgärds variant.

## <a name="mutable-variables"></a>Föränderligt-variabler

Som ett alternativ till att skapa en variabel med `let` , `mutable` skapar nyckelordet en föränderligt-variabel som *kan* bindas igen när den ursprungligen har skapats med hjälp av `set` nyckelordet.

Symboler som har deklarerats och bundits som en del av en `mutable` instruktion kan vara kopplade till ett annat värde senare i koden. Om en symbol har bundits igen senare i koden, ändras inte dess typ och det nya gräns värdet måste vara kompatibelt med den typen.

### <a name="rebinding-of-mutable-symbols"></a>OMBINDNING av föränderligt symboler

En föränderligt-variabel kan bindas om med hjälp av en `set` instruktion.
En sådan OMBINDNING består av nyckelordet `set` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda om symbolerna till och ett avslutande semikolon.

Här ger vi några möjliga exempel på OMBINDNING av instruktions tekniker

### <a name="apply-and-reassign-statements"></a>Uttryck för Apply-och-Reassign

En särskild typ av `set` -sats som vi refererar till som en instruktion för att *tillämpa och omtilldela* är ett bekvämt sätt att sammanfoga om den högra sidan består av en binär Operators program och resultatet måste bindas till det vänstra argumentet till operatorn. Exempel:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
ökar värdet för räknaren `counter` i varje iteration av `for` slingan. Koden ovan motsvarar 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Liknande instruktioner är tillgängliga för alla binära operatorer där typen för den vänstra sidan matchar uttrycks typen. Detta ger till exempel ett bekvämt sätt att ackumulera värden.

Till exempel är supposing `qubits` en regsiter av qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Instruktioner för uppdatering och omtilldelning

Det finns en liknande sammanfogning för [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) på den högra sidan.
Det finns ett uttryck för *uppdatering och omtilldelning* för *namngivna objekt* i användardefinierade typer samt för *mat ris objekt*.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

I [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) våra standard bibliotek finns det nödvändiga verktyg för många vanliga krav för mat ris initiering och manipulering, vilket innebär att du slipper uppdatera mat ris objekt på den första platsen. 

Uppdaterings-och omtilldelnings instruktioner ger ett alternativ om det behövs:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

Med hjälp av biblioteks verktygen för matriser som finns i kan [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) vi till exempel enkelt definiera en funktion som returnerar en matris med Paul, där Pauli vid indexet `i` tar det givna värdet och alla andra poster är identiteten.

Här följer två definitioner av en sådan funktion, med den andra som drar nytta av verktygen i vårt förfogande.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

I stället för att iterera över varje index i matrisen och ange den villkorligt till `PauliI` eller `Pauli` , kan vi istället använda `ConstantArray` från [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) för att skapa en matris `PauliI` och sedan bara returnera ett kopierings-och-uppdatera-uttryck som vi har ändrat specifc-värdet vid indexet `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Tupel och avkonstruktion

Förutom att tilldela en enskild variabel kan `let` `mutable` nyckelorden och,---eller i själva verket andra bindnings konstruktioner, som `set` (beskrivs nedan---), även tillåtas att packa upp innehållet i en [tuple-typ](xref:microsoft.quantum.guide.types#tuple-types).
En tilldelning av det här formuläret är att *avkonstruera* elementen i denna tupel.

Om den högra sidan av bindningen är en tupel, kan denna tupel bli inbyggd vid tilldelningen.
Sådana dekonstruktioner kan omfatta kapslade tupler och all fullständig eller delvis inbyggnad är giltig så länge formen på tuppeln till höger är kompatibel med formen på symbolens tupel.

Ett exempel:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Bindnings omfång

I allmänhet ligger symbol bindningar utanför definitions området och blir instabil i slutet av uttrycks blocket som de inträffar i.
Det finns två undantag till den här regeln:

- Bindningen för loop-variabeln i en `for` slinga är inom omfånget för for-slingan, men inte efter slutet av slingan.
- Alla tre delarna i en `repeat` / `until` slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång, så symboler som är kopplade till bröd texten är tillgängliga i testet och i korrigeringen.

För båda typerna av slingor körs varje steg genom slingan i sin egen omfattning, så bindningar från ett tidigare pass är inte tillgängliga i ett senare pass.
Information om dessa slingor finns i [kontroll flödet](xref:microsoft.quantum.guide.controlflow).

Symbol bindningar från yttre block ärvs av inre block.
En symbol får bara bindas en gång per block. Det är inte tillåtet att definiera en symbol med samma namn som en annan symbol inom omfånget (ingen "skuggning").
Följande sekvenser är juridiska:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

och

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Men detta skulle vara ogiltigt:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

som skulle:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a>Vad står på tur?
Lär dig mer om att [arbeta med qubits](xref:microsoft.quantum.guide.qubits) i Q #.