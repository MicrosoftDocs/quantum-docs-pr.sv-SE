---
title: Arbeta med kvantbitar
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327551"
---
# <a name="working-with-qubits"></a><span data-ttu-id="83904-103">Arbeta med kvantbitar</span><span class="sxs-lookup"><span data-stu-id="83904-103">Working with qubits</span></span>

<span data-ttu-id="83904-104">Nu har vi sett en rad olika delar av språket Q #, så att vi kan komma in på den tjocka och se hur de kan använda qubits.</span><span class="sxs-lookup"><span data-stu-id="83904-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="83904-105">Observera att ingen av dessa instruktioner tillåts i bröd texten i en funktion.</span><span class="sxs-lookup"><span data-stu-id="83904-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="83904-106">De är endast giltiga inom åtgärder.</span><span class="sxs-lookup"><span data-stu-id="83904-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="83904-107">Allokerar qubits</span><span class="sxs-lookup"><span data-stu-id="83904-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="83904-108">Rengör qubits</span><span class="sxs-lookup"><span data-stu-id="83904-108">Clean qubits</span></span>

<span data-ttu-id="83904-109">`using`Instruktionen används för att *allokera* nya qubits för användning under ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="83904-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="83904-110">Instruktionen består av nyckelordet `using` följt av en öppen parentes `(` , en bindning, en avslutande parentes `)` och det instruktions block inom vilket qubits blir tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="83904-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="83904-111">Bindningen följer samma mönster som- `let` instruktioner: antingen en symbol eller en tupel med symboler, följt av ett likhets tecken `=` och antingen ett enda värde eller en matchande tupel av *initierare*.</span><span class="sxs-lookup"><span data-stu-id="83904-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="83904-112">Initierare är tillgängliga antingen för en enskild qubit, anges som `Qubit()` eller en matris med qubits, `Qubit[n]` där `n` är ett `Int` uttryck.</span><span class="sxs-lookup"><span data-stu-id="83904-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="83904-113">Exempel:</span><span class="sxs-lookup"><span data-stu-id="83904-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="83904-114">Alla qubits som tilldelas på det här sättet inleds i $ \ket {0} $ State; i exemplet ovan, `register` är det därför i tillstånd $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="83904-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="83904-115">I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="83904-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="83904-116">Mål datorerna förväntar sig att qubits är i läget $ \ket {0} $ omedelbart före tilldelningen, så att de kan återanvändas och erbjudas till andra `using` block för tilldelning.</span><span class="sxs-lookup"><span data-stu-id="83904-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="83904-117">När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="83904-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="83904-118">Om det behövs kan du använda @"microsoft.quantum.intrinsic.reset" åtgärden för att mäta en qubit i stället och för att använda detta mått resultat för att säkerställa att den uppmätta qubit returneras till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="83904-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="83904-119">Ett sådant mått kommer att förstöra eventuella entanglement med återstående qubits och kan därför påverka beräkningen.</span><span class="sxs-lookup"><span data-stu-id="83904-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="83904-120">Lånade qubits</span><span class="sxs-lookup"><span data-stu-id="83904-120">Borrowed Qubits</span></span>

<span data-ttu-id="83904-121">`borrowing`Instruktionen används för att göra qubits tillgängligt för temporär användning, vilket inte behöver vara i ett särskilt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="83904-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="83904-122">Upplånings metoden gör det möjligt att allokera qubits som kan användas som Scratch-utrymme under en beräkning.</span><span class="sxs-lookup"><span data-stu-id="83904-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="83904-123">Dessa qubits är vanligt vis inte i rent tillstånd, dvs. de är inte nödvändigt vis initierade i ett känt tillstånd, t. ex. $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="83904-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="83904-124">Dessa kallas ofta "smutsig" qubits eftersom deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne.</span><span class="sxs-lookup"><span data-stu-id="83904-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="83904-125">Bindningen följer samma mönster och regler som i en `using` instruktion.</span><span class="sxs-lookup"><span data-stu-id="83904-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="83904-126">Exempel:</span><span class="sxs-lookup"><span data-stu-id="83904-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="83904-127">De lånade qubits är i ett okänt tillstånd och hamnar utanför definitions området i slutet av instruktions blocket.</span><span class="sxs-lookup"><span data-stu-id="83904-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="83904-128">Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånades, d.v.s. deras tillstånd i början och i slutet av instruktions blocket förväntas vara detsamma.</span><span class="sxs-lookup"><span data-stu-id="83904-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="83904-129">Detta tillstånd är i synnerhet inte nödvändigt vis ett klassiskt läge, som i de flesta fall bör låne omfång inte innehålla mätningar.</span><span class="sxs-lookup"><span data-stu-id="83904-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="83904-130">När du lånar qubits försöker systemet först fylla i begäran från qubits som används men som inte har åtkomst till under texten i `borrowing` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="83904-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="83904-131">Om det inte finns tillräckligt med sådan qubits, kommer den att allokera nya qubits för att slutföra begäran.</span><span class="sxs-lookup"><span data-stu-id="83904-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="83904-132">Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.</span><span class="sxs-lookup"><span data-stu-id="83904-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="83904-133">Se exemplet för att [låna qubits](#borrowing-qubits-example) nedan om du vill se ett exempel på hur de används i Q # eller pappers [*faktorn med 2n + 2 qubits med Toffoli-baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för en algoritm som använder lånad qubits.</span><span class="sxs-lookup"><span data-stu-id="83904-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="83904-134">Inre åtgärder</span><span class="sxs-lookup"><span data-stu-id="83904-134">Intrinsic Operations</span></span>

<span data-ttu-id="83904-135">När det har allokerats kan en qubit skickas till funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="83904-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="83904-136">I viss mening är detta allt att ett Q #-program kan utföras med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.</span><span class="sxs-lookup"><span data-stu-id="83904-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="83904-137">Vi kommer att se dessa åtgärder i detalj i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude), men för närvarande nämner vi några användbara åtgärder som kan användas för att interagera med qubits.</span><span class="sxs-lookup"><span data-stu-id="83904-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="83904-138">Först visas qubit Pauli-operatörer $X $, $Y $ och $Z $ i Q # av de inbyggda åtgärderna `X` , `Y` och `Z` som var och en har typen `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="83904-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="83904-139">Som det beskrivs i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude)kan vi tänka på $X $ och därmed `X` en åtgärd med bit vändning eller inte grind.</span><span class="sxs-lookup"><span data-stu-id="83904-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="83904-140">Med den `X` här åtgärden kan vi förbereda tillstånd för formatet $ \ket{s_0 s_1 \dots s_n} $ för en viss klassisk bit-sträng $s $:</span><span class="sxs-lookup"><span data-stu-id="83904-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="83904-141">Senare kommer vi att se fler kompakta sätt att skriva den här åtgärden som inte kräver manuell flödes kontroll.</span><span class="sxs-lookup"><span data-stu-id="83904-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="83904-142">Vi kan också förbereda tillstånd som $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ och $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ genom att använda Hadamard Transform $H $, som representeras i Q # av den inbyggda åtgärden `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="83904-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="83904-143">Mått</span><span class="sxs-lookup"><span data-stu-id="83904-143">Measurements</span></span>

<span data-ttu-id="83904-144">Med hjälp av `Measure` åtgärden, som är en inbyggd icke-enhetlig åtgärd, kan vi extrahera klassisk information från ett objekt av typen `Qubit` och tilldela ett klassiskt värde som ett resultat, som har en reserverad typ `Result` , vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="83904-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="83904-145">Indatamängden till `Measure` är en Pauli axel på Bloch-sfären, som representeras av ett värde av typen `Pauli` (t `PauliX` . ex.) och ett värde av typen `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="83904-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="83904-146">Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet på grund av detta `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="83904-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="83904-147">Ett något mer komplicerat exempel ges av följande åtgärd, som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` är i läget noll när de mäts i en angiven Pauli och som returnerar `false` annars.</span><span class="sxs-lookup"><span data-stu-id="83904-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="83904-148">Exempel på upplåning av qubits</span><span class="sxs-lookup"><span data-stu-id="83904-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="83904-149">I filen Canon finns exempel som använder `borrowing` nyckelordet, till exempel funktionen som `MultiControlledXBorrow` definieras nedan.</span><span class="sxs-lookup"><span data-stu-id="83904-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="83904-150">Om anger `controls` den kontroll-qubits som ska läggas till i en `X` åtgärd, läggs en övergripande del av `Length(controls)-2` många smutsig ancillas till av den här implementeringen.</span><span class="sxs-lookup"><span data-stu-id="83904-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="83904-151">Observera att den omfattande användningen av `With` Combinator----i sitt formulär som är tillämplig för åtgärder som stöder angränsande, d.v.s. `WithA` ---har gjorts i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="83904-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="83904-152">Det här är ett användbart programmerings format eftersom du lägger till kontrollen till strukturer som `With` endast sprider kontroll till den inre åtgärden.</span><span class="sxs-lookup"><span data-stu-id="83904-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="83904-153">Observera att det `body` inte finns någon implementering av `controlled` åtgärdens brödtext, i stället för att lägga till en instruktion, till följd av åtgärden `controlled auto` .</span><span class="sxs-lookup"><span data-stu-id="83904-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="83904-154">Orsaken till detta är att vi vet från strukturen på kretsen som gör det enkelt att lägga till ytterligare kontroller som är fördelaktiga jämfört med att lägga till kontrollen till var och en av varje enskild grind i `body` .</span><span class="sxs-lookup"><span data-stu-id="83904-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="83904-155">Det är en instruktion att jämföra den här koden med en annan Canon `MultiControlledXClean` -funktion som uppnår samma mål för att implementera en multiplicering-kontrollerad `X` åtgärd, men som använder flera rena qubits med `using` mekanismen.</span><span class="sxs-lookup"><span data-stu-id="83904-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="83904-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="83904-156">Next steps</span></span>

<span data-ttu-id="83904-157">Lär dig mer om [kontroll flöde](xref:microsoft.quantum.guide.controlflow) i Q #.</span><span class="sxs-lookup"><span data-stu-id="83904-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>