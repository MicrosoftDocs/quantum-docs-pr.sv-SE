---
title: Arbeta med kvantbitar
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430942"
---
# <a name="working-with-qubits"></a>Arbeta med kvantbitar

Nu har vi sett en rad olika delar av språket Q #, så att vi kan komma in på den tjocka och se hur de kan använda qubits.

Observera att ingen av dessa instruktioner tillåts i bröd texten i en funktion.
De är endast giltiga inom åtgärder.

## <a name="allocating-qubits"></a>Allokerar qubits

### <a name="clean-qubits"></a>Rengör qubits

`using`Instruktionen används för att *allokera* nya qubits för användning under ett instruktions block.

Instruktionen består av nyckelordet `using` följt av en öppen parentes `(` , en bindning, en avslutande parentes `)` och det instruktions block inom vilket qubits blir tillgängligt.
Bindningen följer samma mönster som- `let` instruktioner: antingen en symbol eller en tupel med symboler, följt av ett likhets tecken `=` och antingen ett enda värde eller en matchande tupel av *initierare*.

Initierare är tillgängliga antingen för en enskild qubit, anges som `Qubit()` eller en matris med qubits, `Qubit[n]` där `n` är ett `Int` uttryck.
Exempel:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Alla qubits som tilldelas på det här sättet inleds i $ \ket {0} $ State; i exemplet ovan, `register` är det därför i tillstånd $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.
I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.

> [!WARNING]
> Mål datorerna förväntar sig att qubits är i läget $ \ket {0} $ omedelbart före tilldelningen, så att de kan återanvändas och erbjudas till andra `using` block för tilldelning.
> När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket {0} $.
> Om det behövs kan du använda @"microsoft.quantum.intrinsic.reset" åtgärden för att mäta en qubit i stället och för att använda detta mått resultat för att säkerställa att den uppmätta qubit returneras till $ \ket {0} $. Ett sådant mått kommer att förstöra eventuella entanglement med återstående qubits och kan därför påverka beräkningen.


### <a name="borrowed-qubits"></a>Lånade qubits

`borrowing`Instruktionen används för att göra qubits tillgängligt för temporär användning, vilket inte behöver vara i ett särskilt tillstånd.

Upplånings metoden gör det möjligt att allokera qubits som kan användas som Scratch-utrymme under en beräkning.
Dessa qubits är vanligt vis inte i rent tillstånd, dvs. de är inte nödvändigt vis initierade i ett känt tillstånd, t. ex. $ \ket {0} $.
Dessa kallas ofta "smutsig" qubits eftersom deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne.

Bindningen följer samma mönster och regler som i en `using` instruktion.
Exempel:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
De lånade qubits är i ett okänt tillstånd och hamnar utanför definitions området i slutet av instruktions blocket.
Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånades, d.v.s. deras tillstånd i början och i slutet av instruktions blocket förväntas vara detsamma.
Detta tillstånd är i synnerhet inte nödvändigt vis ett klassiskt läge, som i de flesta fall bör låne omfång inte innehålla mätningar. 

När du lånar qubits försöker systemet först fylla i begäran från qubits som används men som inte har åtkomst till under texten i `borrowing` instruktionen.
Om det inte finns tillräckligt med sådan qubits, kommer den att allokera nya qubits för att slutföra begäran.


Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.
Se exemplet för att [låna qubits](#borrowing-qubits-example) nedan om du vill se ett exempel på hur de används i Q # eller pappers [*faktorn med 2n + 2 qubits med Toffoli-baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för en algoritm som använder lånad qubits.


## <a name="intrinsic-operations"></a>Inre åtgärder

När det har allokerats kan en qubit skickas till funktioner och åtgärder.
I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.
Vi kommer att se dessa åtgärder i detalj i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude), men för närvarande nämner vi några användbara åtgärder som kan användas för att interagera med qubits.

Först visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inbyggda åtgärderna `X` , `Y` och `Z` som var och en har typen `(Qubit => Unit is Adj + Ctl)` .
Som det beskrivs i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude)kan vi tänka på $X $ och därmed `X` en åtgärd med bit vändning eller inte grind.
Med den `X` här åtgärden kan vi förbereda tillstånd för formatet $ \ket{s_0 s_1 \dots s_n} $ för en viss klassisk bit-sträng $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Senare kommer vi att se fler kompakta sätt att skriva den här åtgärden som inte kräver manuell flödes kontroll.

Vi kan också förbereda tillstånd som $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ och $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ genom att använda Hadamard Transform $H $, som representeras i Q # av den inbyggda åtgärden `H : (Qubit => Unit is Adj + Ctl)` :

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Mått

Med hjälp av `Measure` åtgärden, som är en inbyggd icke-enhetlig åtgärd, kan vi extrahera klassisk information från ett objekt av typen `Qubit` och tilldela ett klassiskt värde som ett resultat, som har en reserverad typ `Result` , vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.
Indatamängden till `Measure` är en Pauli axel på Bloch-sfären, som representeras av ett värde av typen `Pauli` (t `PauliX` . ex.) och ett värde av typen `Qubit` .

Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet på grund av detta `PauliZ` .

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Ett något mer komplicerat exempel ges av följande åtgärd, som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` är i läget noll när de mäts i en angiven Pauli och som returnerar `false` annars.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

## <a name="borrowing-qubits-example"></a>Exempel på upplåning av qubits

I filen Canon finns exempel som använder `borrowing` nyckelordet, till exempel funktionen som `MultiControlledXBorrow` definieras nedan.
Om anger `controls` den kontroll-qubits som ska läggas till i en `X` åtgärd, läggs en övergripande del av `Length(controls)-2` många smutsig ancillas till av den här implementeringen.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Observera att den omfattande användningen av `With` Combinator----i sitt formulär som är tillämplig för åtgärder som stöder angränsande, d.v.s. `WithA` ---har gjorts i det här exemplet.
Det här är ett användbart programmerings format eftersom du lägger till kontrollen till strukturer som `With` endast sprider kontroll till den inre åtgärden.
Observera att det `body` inte finns någon implementering av `controlled` åtgärdens brödtext, i stället för att lägga till en instruktion, till följd av åtgärden `controlled auto` .
Orsaken till detta är att vi vet från strukturen på kretsen som gör det enkelt att lägga till ytterligare kontroller som är fördelaktiga jämfört med att lägga till kontrollen till var och en av varje enskild grind i `body` . 

Det är en instruktion att jämföra den här koden med en annan Canon `MultiControlledXClean` -funktion som uppnår samma mål för att implementera en multiplicering-kontrollerad `X` åtgärd, men som använder flera rena qubits med `using` mekanismen. 

## <a name="whats-next"></a>Vad står på tur?
Lär dig mer om [kontroll flöde](xref:microsoft.quantum.guide.controlflow) i Q #.