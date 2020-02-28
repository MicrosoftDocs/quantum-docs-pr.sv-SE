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
# <a name="working-with-qubits"></a><span data-ttu-id="1771a-103">Arbeta med qubits</span><span class="sxs-lookup"><span data-stu-id="1771a-103">Working with Qubits</span></span>

<span data-ttu-id="1771a-104">Nu har vi sett en rad olika delar av språket Q #, så att vi kan komma in på den tjocka och se hur de kan använda qubits.</span><span class="sxs-lookup"><span data-stu-id="1771a-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="1771a-105">Allokerar qubits</span><span class="sxs-lookup"><span data-stu-id="1771a-105">Allocating Qubits</span></span>

<span data-ttu-id="1771a-106">För att få en qubit som vi kan använda i Q # *allokerar* vi qubits inom ett `using` block:</span><span class="sxs-lookup"><span data-stu-id="1771a-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="1771a-107">Alla qubits som har allokerats på det här sättet börjar inaktive ras i $ \ket{0}$ State; i exemplet ovan är `register` därför i tillstånd $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1771a-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="1771a-108">I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="1771a-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="1771a-109">Mål datorerna förväntar sig att qubits är i läget $ \ket{0}$ omedelbart före tilldelningen, så att de kan återanvändas och erbjudas till andra `using` block för tilldelning.</span><span class="sxs-lookup"><span data-stu-id="1771a-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="1771a-110">När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1771a-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="1771a-111">Vid behov kan @"microsoft.quantum.intrinsic.reset"-åtgärden användas för att mäta en qubit i stället och för att använda detta mått resultat för att säkerställa att den uppmätta qubit returneras till $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1771a-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="1771a-112">Ett sådant mått kommer att förstöra eventuella entanglement med återstående qubits och kan därför påverka beräkningen.</span><span class="sxs-lookup"><span data-stu-id="1771a-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="1771a-113">Inre åtgärder</span><span class="sxs-lookup"><span data-stu-id="1771a-113">Intrinsic Operations</span></span>

<span data-ttu-id="1771a-114">När det har allokerats kan en qubit skickas till funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1771a-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="1771a-115">I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1771a-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="1771a-116">Vi kommer att se dessa åtgärder i detalj i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude), men för närvarande nämner vi några användbara åtgärder som kan användas för att interagera med qubits.</span><span class="sxs-lookup"><span data-stu-id="1771a-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="1771a-117">För det första visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inre åtgärderna `X`, `Y`och `Z`, som var och en har typen `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="1771a-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="1771a-118">Som det beskrivs i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude)kan vi tänka på $X $ och därmed `X` som en åtgärd för att vända eller inte Gate.</span><span class="sxs-lookup"><span data-stu-id="1771a-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="1771a-119">Med åtgärden `X` kan vi förbereda tillstånden för formatet $ \ket{s_0 s_1 \dots s_n} $ för viss klassisk bit-sträng $s $:</span><span class="sxs-lookup"><span data-stu-id="1771a-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="1771a-120">Senare kommer vi att se fler kompakta sätt att skriva den här åtgärden som inte kräver manuell flödes kontroll.</span><span class="sxs-lookup"><span data-stu-id="1771a-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="1771a-121">Vi kan också förbereda tillstånd som $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ och $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ genom att använda Hadamard Transform $H $, som representeras i Q # av den inre åtgärden `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="1771a-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="1771a-122">Mått</span><span class="sxs-lookup"><span data-stu-id="1771a-122">Measurements</span></span>

<span data-ttu-id="1771a-123">Med hjälp av `Measure`-åtgärden, som är en inbyggd inbyggd icke-enhetlig åtgärd, kan vi extrahera klassisk information från ett objekt av typen `Qubit` och tilldela ett klassiskt värde som ett resultat, som har en reserverad typ `Result`, vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="1771a-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="1771a-124">Inmatade `Measure` är en Pauli axel på Bloch-sfären, som representeras av ett värde av typen `Pauli` (till exempel `PauliX`) och ett värde av typen `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="1771a-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="1771a-125">Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket{0}$ State, och sedan tillämpar en Hadamard-åtgärd `H` till den och mäter resultatet i `PauliZ`-basen.</span><span class="sxs-lookup"><span data-stu-id="1771a-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="1771a-126">Ett något mer komplicerat exempel ges av följande åtgärd, som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` har värdet noll när de mäts i en angiven Pauli och som returnerar `false` annars.</span><span class="sxs-lookup"><span data-stu-id="1771a-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="1771a-127">Med hjälp av Q #-språket kan ett klassiskt kontroll flöde vara beroende av resultatet av att mäta qubits.</span><span class="sxs-lookup"><span data-stu-id="1771a-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="1771a-128">Den här funktionen aktiverar implementering av kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.</span><span class="sxs-lookup"><span data-stu-id="1771a-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="1771a-129">Som exempel är det enkelt att implementera så kallade ru: er-mönster ( *REPEAT-until-lyckades* ) i Q #.</span><span class="sxs-lookup"><span data-stu-id="1771a-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="1771a-130">Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar, men för vilka den faktiska kostnaden är beroende av en faktisk körning och en faktisk Interfoliering av olika möjliga grenar.</span><span class="sxs-lookup"><span data-stu-id="1771a-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="1771a-131">För att under lätta upprepnings-tills-lyckat (ru: er) mönster, stöder Q # konstruktionen</span><span class="sxs-lookup"><span data-stu-id="1771a-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="1771a-132">där `statementBlock1` och `statementBlock2` är noll eller fler Q #-instruktioner och `expression` ett giltigt uttryck som utvärderas till ett värde av typen `Bool`.</span><span class="sxs-lookup"><span data-stu-id="1771a-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="1771a-133">I ett vanligt användnings fall implementerar följande Q #-åtgärd en rotation runt en onormal axel om $ (I + 2i Z)/\sqrt{5}$ på Bloch-sfären.</span><span class="sxs-lookup"><span data-stu-id="1771a-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="1771a-134">Detta åstadkoms med hjälp av ett känt ru: er-mönster:</span><span class="sxs-lookup"><span data-stu-id="1771a-134">This is accomplished by using a known RUS pattern:</span></span>

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

<span data-ttu-id="1771a-135">I det här exemplet visas användningen av en föränderligt-variabel `finished` som ligger inom omfånget för hela upprepnings-tills-korrigering-slingan och som initieras före loopen och uppdateras i korrigerings steget.</span><span class="sxs-lookup"><span data-stu-id="1771a-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="1771a-136">Slutligen visar vi ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, med början från $ \ket{+} $ State.</span><span class="sxs-lookup"><span data-stu-id="1771a-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="1771a-137">Se även [exempel på enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="1771a-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

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

<span data-ttu-id="1771a-138">Viktiga programmerings funktioner som visas i den här åtgärden är en mer komplex `fixup` del av slingan, vilket inbegriper Quantum-åtgärder och användningen av `AssertProb`-uttryck för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.</span><span class="sxs-lookup"><span data-stu-id="1771a-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="1771a-139">Se även [testning och fel sökning](xref:microsoft.quantum.techniques.testing-and-debugging) för mer information om [`Assert`](xref:microsoft.quantum.intrinsic.assert) och [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1771a-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
