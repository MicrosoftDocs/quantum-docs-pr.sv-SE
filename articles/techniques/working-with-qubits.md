---
title: Arbeta med qubits | Microsoft Docs
description: Arbeta med qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183479"
---
# <a name="working-with-qubits"></a>Arbeta med qubits #

Nu har vi sett en rad olika delar av språket Q #, så att vi kan komma in på den tjocka och se hur de kan använda qubits.

## <a name="allocating-qubits"></a>Allokerar qubits ##

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

## <a name="intrinsic-operations"></a>Inre åtgärder ##

När det har allokerats kan en qubit skickas till funktioner och åtgärder.
I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.
Vi kommer att se dessa åtgärder i detalj i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude), men för närvarande nämner vi några användbara åtgärder som kan användas för att interagera med qubits.

För det första visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inre åtgärderna `X`, `Y`och `Z`, som var och en har typen `(Qubit => Unit is Adj + Ctl)`.
Som det beskrivs i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude)kan vi tänka på $X $ och därmed `X` som en åtgärd för att vända eller inte Gate.
Detta gör att vi kan förbereda tillstånd av formatet $ \ket{s_0 s_1 \dots s_n} $ för en viss klassisk bit-sträng $s $:

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Senare kommer vi att se fler kompakta sätt att skriva den här åtgärden som inte kräver manuell flödes kontroll.

Vi kan också förbereda tillstånd som $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ och $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ med hjälp av Hadamard Transform $H $ , som representeras i Q # av den inbyggda åtgärden `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Mått ##

Med hjälp av `Measure`-åtgärden, som är en inbyggd icke-enhetlig åtgärd, kan vi extrahera klassisk information från ett objekt av typen `Qubit` och tilldela ett klassiskt värde som ett resultat, som har en reserverad typ `Result`, vilket indikerar att resultatet inte är det längre ett Quantum-tillstånd. Indatamängden till `Measure` är en Pauli axel på Bloch-sfären som representeras av ett objekt av typen `Pauli` (t. ex., till exempel `PauliX`) och ett objekt av typen `Qubit`. 

Ett enkelt exempel är följande åtgärd som skapar en qubit i $ \ket{0}$ State, och som sedan tillämpar en Hadamard-grind ``H`` till den och sedan mäter resultatet i `PauliZ`-basen. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

Ett något mer komplicerat exempel ges av följande åtgärd som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` är noll, när de mäts i en angiven Pauli och `false` annars. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Q #-språket tillåter beroenden av klassiskt kontroll flöde på mätnings resultatet av qubits. På så sätt kan du implementera kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries. Som exempel är det enkelt att implementera så att det anropas *upprepas tills det lyckas* i Q #, som är Probabilistic-kretsar som har en *förväntad* låg kostnad i termer av elementära grindar, men som den faktiska kostnaden beror på för en faktisk körning och en faktisk Interfoliering av olika möjliga grenar. 

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
där `statementBlock1` och `statementBlock2` är noll eller fler Q #-instruktioner och `expression` ett giltigt uttryck som utvärderas till ett värde av typen `Bool`. I ett vanligt användnings fall implementerar följande krets en rotation runt en onormal axel om $ (I + 2i Z)/\sqrt{5}$ på Bloch-sfären. Detta åstadkoms med hjälp av ett känt ru: er-mönster: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

I det här exemplet visas användningen av en föränderligt-variabel `finished` som ligger inom omfånget för hela upprepnings-tills-korrigering-slingan och som initieras före loopen och uppdateras i korrigerings steget.

Slutligen visar vi ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, med början från $ \ket{+} $ State. Se även [exempel på enhets testning som tillhandahålls med standard biblioteket](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Viktiga programmerings funktioner som visas i den här åtgärden är en mer komplex `fixup` del av slingan som inbegriper Quantum-åtgärder och användningen av `AssertProb`-uttryck för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i hämtas. Mer information om `Assert` och `AssertProb`-instruktioner finns i [testa och felsöka](xref:microsoft.quantum.techniques.testing-and-debugging) . 
