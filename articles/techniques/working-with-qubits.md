---
title: Arbeta med qubits
description: Lär dig hur du allokerar qubits, använder dem i åtgärder och funktioner och mäter resultatet.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907655"
---
# <a name="working-with-qubits"></a>Arbeta med qubits

Nu har vi sett en rad olika delar av språket Q #, så att vi kan komma in på den tjocka och se hur de kan använda qubits.

## <a name="allocating-qubits"></a>Allokerar qubits

För att få en qubit som vi kan använda i Q # *allokerar* vi qubits inom ett `using` block:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Alla qubits som har allokerats på det här sättet börjar inaktive ras i $ \ket{0}$ State; i exemplet ovan är `register` därför i tillstånd $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.

> [!WARNING]
> Mål datorerna förväntar sig att qubits är i läget $ \ket{0}$ omedelbart före tilldelningen, så att de kan återanvändas och erbjudas till andra `using` block för tilldelning.
> När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket{0}$.
> Vid behov kan @"microsoft.quantum.intrinsic.reset"-åtgärden användas för att mäta en qubit i stället och för att använda detta mått resultat för att säkerställa att den uppmätta qubit returneras till $ \ket{0}$. Ett sådant mått kommer att förstöra eventuella entanglement med återstående qubits och kan därför påverka beräkningen.

## <a name="intrinsic-operations"></a>Inre åtgärder

När det har allokerats kan en qubit skickas till funktioner och åtgärder.
I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.
Vi kommer att se dessa åtgärder i detalj i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude), men för närvarande nämner vi några användbara åtgärder som kan användas för att interagera med qubits.

För det första visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inre åtgärderna `X`, `Y`och `Z`, som var och en har typen `(Qubit => Unit is Adj + Ctl)`.
Som det beskrivs i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude)kan vi tänka på $X $ och därmed `X` som en åtgärd för att vända eller inte Gate.
Med åtgärden `X` kan vi förbereda tillstånden för formatet $ \ket{s_0 s_1 \dots s_n} $ för viss klassisk bit-sträng $s $:

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

Vi kan också förbereda tillstånd som $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ och $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ genom att använda Hadamard Transform $H $, som representeras i Q # av den inre åtgärden `H : (Qubit => Unit is Adj + Ctl)`:

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

Med hjälp av `Measure`-åtgärden, som är en inbyggd inbyggd icke-enhetlig åtgärd, kan vi extrahera klassisk information från ett objekt av typen `Qubit` och tilldela ett klassiskt värde som ett resultat, som har en reserverad typ `Result`, vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.
Inmatade `Measure` är en Pauli axel på Bloch-sfären, som representeras av ett värde av typen `Pauli` (till exempel `PauliX`) och ett värde av typen `Qubit`.

Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket{0}$ State, och sedan tillämpar en Hadamard-åtgärd `H` till den och mäter resultatet i `PauliZ`-basen.

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

Ett något mer komplicerat exempel ges av följande åtgärd, som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` har värdet noll när de mäts i en angiven Pauli och som returnerar `false` annars.

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

Med hjälp av Q #-språket kan ett klassiskt kontroll flöde vara beroende av resultatet av att mäta qubits.
Den här funktionen aktiverar implementering av kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.
Som exempel är det enkelt att implementera så kallade ru: er-mönster ( *REPEAT-until-lyckades* ) i Q #.
Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar, men för vilka den faktiska kostnaden är beroende av en faktisk körning och en faktisk Interfoliering av olika möjliga grenar.

För att under lätta upprepnings-tills-lyckat (ru: er) mönster, stöder Q # konstruktionen

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

där `statementBlock1` och `statementBlock2` är noll eller fler Q #-instruktioner och `expression` ett giltigt uttryck som utvärderas till ett värde av typen `Bool`.
I ett vanligt användnings fall implementerar följande Q #-åtgärd en rotation runt en onormal axel om $ (I + 2i Z)/\sqrt{5}$ på Bloch-sfären. Detta åstadkoms med hjälp av ett känt ru: er-mönster:

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

I det här exemplet visas användningen av en föränderligt-variabel `finished` som ligger inom omfånget för hela upprepnings-tills-korrigering-slingan och som initieras före loopen och uppdateras i korrigerings steget.

Slutligen visar vi ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, med början från $ \ket{+} $ State.
Se även [exempel på enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
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

Viktiga programmerings funktioner som visas i den här åtgärden är en mer komplex `fixup` del av slingan, vilket inbegriper Quantum-åtgärder och användningen av `AssertProb`-uttryck för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.
Se även [testning och fel sökning](xref:microsoft.quantum.techniques.testing-and-debugging) för mer information om [`Assert`](xref:microsoft.quantum.intrinsic.assert) och [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) åtgärder.
