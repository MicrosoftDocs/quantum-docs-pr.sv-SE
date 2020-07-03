---
title: 'Variabler i Q #'
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885286"
---
# <a name="variables-in-q"></a>Variabler i Q #

Q # skiljer sig mellan föränderligt och oföränderliga symboler, eller *variabler*som är kopplade till/tilldelas till uttryck.
I allmänhet uppmuntras användningen av oföränderliga symboler eftersom den tillåter kompilatorn att utföra mer optimeringar.

Den vänstra sidan av en bindning består av en symbol tupel och högra sidan av ett uttryck.

## <a name="immutable-variables"></a>Variabler som inte är oföränderlig

Du kan tilldela ett värde av vilken typ som helst i Q # till en variabel för åter användning i en åtgärd eller funktion med hjälp av `let` nyckelordet. 

En oföränderlig bindning består av nyckelordet `let` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda symbolerna till och ett avslutande semikolon.

Till exempel:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Detta tilldelar en viss matris av Pauli-operatörer till variabel namnet (eller symbol) `measurementOperator` .

> [!NOTE]
> I föregående exempel behöver du inte uttryckligen ange typen för den nya variabeln, eftersom uttrycket till höger i `let` instruktionen är entydigt, och kompilatorn härleder rätt typ. 

Variabler som definieras med `let` är *oföränderliga*, vilket innebär att du inte längre kan ändra det när du har definierat det.
Detta möjliggör flera betalnings optimeringar, inklusive optimering av den klassiska logiken som används i variabler för att sorteras om för att tillämpa `Adjoint` en åtgärds variant.

## <a name="mutable-variables"></a>Föränderligt-variabler

Som ett alternativ till att skapa en variabel med `let` , `mutable` skapar nyckelordet en föränderligt-variabel som *kan* bindas om när den ursprungligen har skapats med hjälp av `set` nyckelordet.

Du kan binda om symboler som har deklarerats och bundits som en del av en `mutable` instruktion till ett annat värde senare i koden. Om en symbol har bundits igen senare i koden, ändras inte dess typ och det nya gräns värdet måste vara kompatibelt med den typen.

### <a name="rebinding-of-mutable-symbols"></a>OMBINDNING av föränderligt symboler

Du kan binda om en föränderligt-variabel med hjälp av en `set` instruktion.
En sådan OMBINDNING består av nyckelordet `set` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda om symbolerna till och ett avslutande semikolon.

Här följer några exempel på OMBINDNING av instruktions tekniker.

#### <a name="apply-and-reassign-statements"></a>Uttryck för Apply-och-Reassign

En särskild typ av `set` sats, uttrycket *Apply-och-Reassign* , är ett bekvämt sätt att sammanfoga om den högra sidan består av en binär Operators program, och resultatet måste bindas till det vänstra argumentet till operatorn. Exempel:

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
ökar värdet för räknaren `counter` i varje iteration av `for` slingan. Föregående kod motsvarar 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Liknande instruktioner är tillgängliga för alla binära operatorer där typen för den vänstra sidan matchar uttrycks typen. Dessa uttryck ger ett bekvämt sätt att ackumulera värden.

Till exempel är supposing `qubits` ett register över qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Instruktioner för uppdatering och omtilldelning

Det finns en liknande sammanfogning för [kopierings-och uppdaterings uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) på den högra sidan.
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

Om det finns matriser [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) innehåller standard biblioteket för Q # de verktyg som krävs för många vanliga behov av initiering och manipulering av matris, och därför kan du undvika att behöva uppdatera mat ris objekt på den första platsen. 

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

Med hjälp av biblioteks verktygen för matriser som finns i [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , kan du till exempel enkelt definiera en funktion som returnerar en matris med `Pauli` typer där elementet i indexet `i` tar ett givet `Pauli` värde, och alla andra poster är identiteten ( `PauliI` ).

Här följer två definitioner av en sådan funktion, med den andra som drar nytta av verktygen i vårt förfogande.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

I stället för att iterera över varje index i matrisen och villkorligt ange det till `PauliI` eller angivet `pauli` , kan du i stället använda `ConstantArray` från [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) för att skapa en mat ris `PauliI` typ och sedan bara returnera ett kopierings-och-uppdatera-uttryck där du har ändrat det aktuella värdet vid indexet `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Tupel och avkonstruktion

Förutom att tilldela en enskild variabel kan du använda `let` nyckelorden och, `mutable` eller någon annan bindnings konstruktion, till exempel `set` för att packa upp innehållet i en tuple- [typ](xref:microsoft.quantum.guide.types#tuple-types).
En tilldelning av det här formuläret är att *avkonstruera* elementen i denna tupel.

Om bindningens högra sida är en tupel kan du dekonstruera denna tupel vid tilldelning.
Sådana dekonstruktioner kan omfatta kapslade tupler och all fullständig eller delvis inbyggnad är giltig så länge formen på tuppeln på den högra sidan är kompatibel med symbolens tuple-form.

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
- Alla tre delarna i en `repeat` / `until` slinga (bröd texten, testet och korrigeringen) fungerar som ett enda omfång, så symboler som är kopplade till bröd texten är tillgängliga i testet och korrigeringen.

För båda typerna av slingor körs varje pass genom slingan i sin egen omfattning, så bindningar från ett tidigare pass är inte tillgängliga i ett senare pass.
Mer information om dessa slingor finns i [kontroll flöde](xref:microsoft.quantum.guide.controlflow).

Inre block ärver symbol bindningar från yttre block.
Du kan bara binda en symbol en gång per block. Det är inte tillåtet att definiera en symbol med samma namn som en annan symbol inom omfånget (ingen "skuggning").
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

## <a name="next-steps"></a>Nästa steg

Lär dig mer om att [arbeta med qubits](xref:microsoft.quantum.guide.qubits) i Q #.