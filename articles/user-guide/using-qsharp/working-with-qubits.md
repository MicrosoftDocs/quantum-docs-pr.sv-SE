---
title: Arbeta med kvantbitar
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885305"
---
# <a name="working-with-qubits"></a>Arbeta med kvantbitar

Qubits är det grundläggande informations objektet i Quantum Computing. En allmän introduktion till qubits finns i [förstå Quantum Computing](xref:microsoft.quantum.overview.understanding)och för att gå djupare till deras matematiska åter givning, se [qubit](xref:microsoft.quantum.concepts.qubit). 

I den här artikeln lär du dig hur du använder och arbetar med qubits i ett Q #-program. 

> [!IMPORTANT]
>Ingen av de instruktioner som beskrivs i den här artikeln är giltiga i bröd texten i en funktion. De är endast giltiga inom åtgärder.

## <a name="allocating-qubits"></a>Allokerar qubits

Eftersom fysiska qubits är en värdefull resurs på en Quantum-dator är en del av kompilatorns jobb att se till att de används så effektivt som möjligt.
Därför måste du ange att Q # ska *tilldela* qubits för användning i ett visst instruktions block.
Du kan allokera qubits som en enda qubit, eller som en matris med qubits, som kallas *Registrera*. 

### <a name="clean-qubits"></a>Rengör qubits

Använd `using` instruktionen för att allokera nya qubits för användning under ett instruktions block.

Instruktionen består av nyckelordet `using` följt av en bindning omgiven av parenteser `( )` och det instruktions block inom vilket qubits är tillgängligt.
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

Alla qubits som allokeras på det här sättet börjar inaktive ras i $ \ket {0} $-tillstånd. I föregående exempel `auxiliary` är ett enda qubit i status $ \ket {0} $ och `register` är i fem qubit State $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.
I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.

> [!WARNING]
> Mål datorer kan återanvända friallokerade qubits och erbjuda dem till andra `using` block för tilldelning. På så sätt förväntar sig mål datorn att qubits är i läget $ \ket {0} $ omedelbart före tilldelningen.
> När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket {0} $.
> Om det behövs kan du använda @"microsoft.quantum.intrinsic.reset" åtgärden, som returnerar qubit till $ \ket {0} $ genom att mäta den och utföra en åtgärd baserat på resultatet. En sådan mätning förstör alla entanglement med återstående qubits och kan därför påverka beräkningen.


### <a name="borrowed-qubits"></a>Lånade qubits

Använd `borrowing` instruktionen för att allokera qubits för tillfällig användning som inte behöver vara i ett särskilt tillstånd.

Du kan använda lånade qubits som arbets yta under en beräkning.
Dessa qubits är vanligt vis inte i rent tillstånd, det vill säga att de inte nödvändigt vis initieras i ett känt tillstånd, t. ex. $ \ket {0} $.
Dessa kallas ofta "smutsig" qubits eftersom deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne.

Bindningen följer samma mönster och regler som `using` instruktionen.
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
Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånade ut dem. det vill säga deras tillstånd i början och slutet av instruktions blocket ska vara detsamma.
Eftersom det här läget inte är ett klassiskt läge bör det i de flesta fall lånade omfattningarna inte innehålla några mätningar. 

När du lånar qubits försöker systemet först fylla i begäran från qubits som används men inte har åtkomst till under texten i `borrowing` utdraget.
Om det inte finns tillräckligt med sådana qubits, allokerar den nya qubits för att slutföra begäran.

Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.
Ett exempel på hur de används i Q # finns i avsnittet om att [låna qubits-exempel](#borrowing-qubits-example) i den här artikeln, eller pappers [*faktorn med 2n + 2 qubits med Toffoli-baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för en algoritm som använder lånad qubits.

## <a name="intrinsic-operations"></a>Inre åtgärder

När du har allokerat kan du skicka en qubit till funktioner och åtgärder.
I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.

I den här artikeln beskrivs några användbara Q #-åtgärder som du kan använda för att interagera med qubits.
Mer information om dessa och andra finns i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude). 

Först visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inbyggda åtgärderna [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) och [`Z`](xref:microsoft.quantum.intrinsic.z) som var och en har typen `(Qubit => Unit is Adj + Ctl)` .

Som det beskrivs i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude)kan du tänka på $X $ och därmed `X` en åtgärd med bit vändning eller inte grind.
Du kan använda `X` åtgärden för att förbereda statusarna i formatet $ \ket{s_0 s_1 \dots s_n} $ för viss klassisk bit-sträng $s $:

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Senare visas fler kompakta sätt att skriva den här åtgärden som inte kräver manuellt kontroll flöde.

Du kan också förbereda tillstånd som $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ och $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ genom att använda Hadamard Transform $H $, som representeras i Q # av den inre åtgärden [`H`](xref:microsoft.quantum.intrinsic.h) (även av typen (qubit => Unit rejust + CTL) "):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Mått

Mätningar av enskilda qubits kan utföras i olika baser, varje representeras av en Pauli-axel på [Bloch-sfären](xref:microsoft.quantum.glossary#bloch-sphere).
*Beräknings basen* avser `PauliZ` basen och är den vanligaste användnings punkten för mått.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Mäta en enskild qubit baserat på `PauliZ`

Använd [`M`](xref:microsoft.quantum.intrinsic.m) åtgärden, som är en inbyggd icke-enhetlig drift, för att mäta en enskild qubit i `PauliZ` grunden och tilldela ett klassiskt värde till resultatet.
`M`har en reserverad returtyp, `Result` som endast kan ta värden `Zero` eller `One` som motsvarar de uppmätta tillstånden $ \ket {0} $ eller $ \ket {1} $ – vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.

Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet på grund av detta `PauliZ` .

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Mät en eller flera qubits i vissa baser

Om du vill mäta en matris med en eller flera qubits i vissa baser kan du använda [`Measure`](xref:microsoft.quantum.intrinsic.measure) åtgärden.

Indatan till `Measure` är en matris med `Pauli` typer (till exempel `[PauliX, PauliZ, PauliZ]` ) och en matris med qubits.

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

Observera att det här exemplet fortfarande bara utför `Measure` en enskild qubits i taget, men åtgärden kan utökas till gemensamma mått på flera qubits.

## <a name="borrowing-qubits-example"></a>Exempel på upplåning av qubits

Det finns exempel i Canon som använder `borrowing` nyckelordet, till exempel följande funktion `MultiControlledXBorrow` . Om anger `controls` vilka kontroll-qubits som ska läggas till i en `X` åtgärd är antalet [ancillas](xref:microsoft.quantum.glossary#ancilla) som har lagts till av den här implementeringen `Length(controls)-2` .

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

Observera att det här exemplet använde en omfattande användning av `With` Combinator, i dess form som är tillämpligt för åtgärder som stöder angränsande, t. ex `WithA` ..
Det här är ett användbart programmerings format eftersom du lägger till kontrollen till strukturer som `With` endast sprider kontroll till den inre åtgärden.
Observera också att `body` en implementering av `controlled` Åtgärds innehållet uttryckligen tillhandahölls, förutom för åtgärden, i stället för att skicka en `controlled auto` instruktion.
Orsaken till detta är att på grund av krets strukturen, är det enkelt att lägga till ytterligare kontroller, vilket är fördelaktigt jämfört med att lägga till kontrollen i varje grind i `body` . 

Det är en instruktion att jämföra den här koden med en annan Canon `MultiControlledXClean` -funktion som uppnår samma mål för att implementera en multiplicering-kontrollerad `X` åtgärd, men som använder flera rena qubits med `using` mekanismen. 

## <a name="next-steps"></a>Nästa steg

Lär dig mer om [kontroll flöde](xref:microsoft.quantum.guide.controlflow) i Q #.