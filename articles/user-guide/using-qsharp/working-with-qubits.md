---
title: Arbeta med kvantbitar
description: fyllnings Beskrivning
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867870"
---
# <a name="working-with-qubits"></a><span data-ttu-id="a7f54-103">Arbeta med kvantbitar</span><span class="sxs-lookup"><span data-stu-id="a7f54-103">Working with qubits</span></span>

<span data-ttu-id="a7f54-104">Qubits är det grundläggande informations objektet i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="a7f54-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="a7f54-105">En allmän introduktion till qubits finns i [förstå Quantum Computing](xref:microsoft.quantum.overview.understanding)och för att gå djupare till deras matematiska åter givning, se [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="a7f54-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="a7f54-106">I den här artikeln lär du dig hur du använder och arbetar med qubits i ett Q# program.</span><span class="sxs-lookup"><span data-stu-id="a7f54-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="a7f54-107">Ingen av de instruktioner som beskrivs i den här artikeln är giltiga i bröd texten i en funktion.</span><span class="sxs-lookup"><span data-stu-id="a7f54-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="a7f54-108">De är endast giltiga inom åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a7f54-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="a7f54-109">Allokerar qubits</span><span class="sxs-lookup"><span data-stu-id="a7f54-109">Allocating Qubits</span></span>

<span data-ttu-id="a7f54-110">Eftersom fysiska qubits är en värdefull resurs på en Quantum-dator är en del av kompilatorns jobb att se till att de används så effektivt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="a7f54-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="a7f54-111">Därför måste du ange Q# att *allokera* qubits för användning i ett visst instruktions block.</span><span class="sxs-lookup"><span data-stu-id="a7f54-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="a7f54-112">Du kan allokera qubits som en enda qubit, eller som en matris med qubits, som kallas *Registrera*.</span><span class="sxs-lookup"><span data-stu-id="a7f54-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="a7f54-113">Rengör qubits</span><span class="sxs-lookup"><span data-stu-id="a7f54-113">Clean qubits</span></span>

<span data-ttu-id="a7f54-114">Använd `using` instruktionen för att allokera nya qubits för användning under ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="a7f54-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="a7f54-115">Instruktionen består av nyckelordet `using` följt av en bindning omgiven av parenteser `( )` och det instruktions block inom vilket qubits är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="a7f54-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="a7f54-116">Bindningen följer samma mönster som- `let` instruktioner: antingen en symbol eller en tupel med symboler, följt av ett likhets tecken `=` och antingen ett enda värde eller en matchande tupel av *initierare*.</span><span class="sxs-lookup"><span data-stu-id="a7f54-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="a7f54-117">Initierare är tillgängliga antingen för en enskild qubit, anges som `Qubit()` eller en matris med qubits, `Qubit[n]` där `n` är ett `Int` uttryck.</span><span class="sxs-lookup"><span data-stu-id="a7f54-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="a7f54-118">Exempel:</span><span class="sxs-lookup"><span data-stu-id="a7f54-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="a7f54-119">Alla qubits som allokeras på det här sättet börjar inaktive ras i $ \ket {0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a7f54-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="a7f54-120">I föregående exempel `auxiliary` är ett enda qubit i status $ \ket {0} $ och `register` är i fem qubit State $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a7f54-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="a7f54-121">I slutet av `using` blocket frigörs alla qubits som tilldelas av det blocket omedelbart och kan inte användas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="a7f54-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="a7f54-122">Mål datorer kan återanvända friallokerade qubits och erbjuda dem till andra `using` block för tilldelning.</span><span class="sxs-lookup"><span data-stu-id="a7f54-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="a7f54-123">På så sätt förväntar sig mål datorn att qubits är i läget $ \ket {0} $ omedelbart före tilldelningen.</span><span class="sxs-lookup"><span data-stu-id="a7f54-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="a7f54-124">När det är möjligt kan du använda enhetlig drift för att returnera tilldelade qubits till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a7f54-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="a7f54-125">Om det behövs kan du använda @"microsoft.quantum.intrinsic.reset" åtgärden, som returnerar qubit till $ \ket {0} $ genom att mäta den och utföra en åtgärd baserat på resultatet.</span><span class="sxs-lookup"><span data-stu-id="a7f54-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="a7f54-126">En sådan mätning förstör alla entanglement med återstående qubits och kan därför påverka beräkningen.</span><span class="sxs-lookup"><span data-stu-id="a7f54-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="a7f54-127">Lånade qubits</span><span class="sxs-lookup"><span data-stu-id="a7f54-127">Borrowed Qubits</span></span>

<span data-ttu-id="a7f54-128">Använd `borrowing` instruktionen för att allokera qubits för tillfällig användning som inte behöver vara i ett särskilt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a7f54-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="a7f54-129">Du kan använda lånade qubits som arbets yta under en beräkning.</span><span class="sxs-lookup"><span data-stu-id="a7f54-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="a7f54-130">Dessa qubits är vanligt vis inte i rent tillstånd, det vill säga att de inte nödvändigt vis initieras i ett känt tillstånd, t. ex. $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a7f54-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="a7f54-131">Dessa kallas ofta "smutsig" qubits eftersom deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne.</span><span class="sxs-lookup"><span data-stu-id="a7f54-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="a7f54-132">Bindningen följer samma mönster och regler som `using` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="a7f54-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="a7f54-133">Exempel:</span><span class="sxs-lookup"><span data-stu-id="a7f54-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="a7f54-134">De lånade qubits är i ett okänt tillstånd och hamnar utanför definitions området i slutet av instruktions blocket.</span><span class="sxs-lookup"><span data-stu-id="a7f54-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="a7f54-135">Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånade ut dem. det vill säga deras tillstånd i början och slutet av instruktions blocket ska vara detsamma.</span><span class="sxs-lookup"><span data-stu-id="a7f54-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="a7f54-136">Eftersom det här läget inte är ett klassiskt läge bör det i de flesta fall lånade omfattningarna inte innehålla några mätningar.</span><span class="sxs-lookup"><span data-stu-id="a7f54-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="a7f54-137">När du lånar qubits försöker systemet först fylla i begäran från qubits som används men inte har åtkomst till under texten i `borrowing` utdraget.</span><span class="sxs-lookup"><span data-stu-id="a7f54-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="a7f54-138">Om det inte finns tillräckligt med sådana qubits, allokerar den nya qubits för att slutföra begäran.</span><span class="sxs-lookup"><span data-stu-id="a7f54-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="a7f54-139">Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.</span><span class="sxs-lookup"><span data-stu-id="a7f54-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="a7f54-140">Ett exempel på hur de används i Q# finns i avsnittet om [upplåning av qubits](#borrowing-qubits-example) i den här artikeln, eller pappers [*faktorn med 2n + 2 qubits med Toffoli baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för en algoritm som använder lånad qubits.</span><span class="sxs-lookup"><span data-stu-id="a7f54-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="a7f54-141">Inre åtgärder</span><span class="sxs-lookup"><span data-stu-id="a7f54-141">Intrinsic Operations</span></span>

<span data-ttu-id="a7f54-142">När du har allokerat kan du skicka en qubit till funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a7f54-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="a7f54-143">I en viss mening är detta allt som ett Q# program kan göra med en qubit, eftersom de åtgärder som kan vidtas är definierade som åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a7f54-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="a7f54-144">I den här artikeln beskrivs några användbara Q# åtgärder som du kan använda för att interagera med qubits.</span><span class="sxs-lookup"><span data-stu-id="a7f54-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="a7f54-145">Mer information om dessa och andra finns i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="a7f54-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="a7f54-146">Först, qubit Pauli-operatörerna $X $, $Y $ och $Z $, representeras Q# av de inbyggda åtgärderna [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) och [`Z`](xref:microsoft.quantum.intrinsic.z) , var och en av dessa är av typen `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a7f54-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="a7f54-147">Som det beskrivs i de [inre driften och funktionerna](xref:microsoft.quantum.libraries.standard.prelude)kan du tänka på $X $ och därmed `X` en åtgärd med bit vändning eller inte grind.</span><span class="sxs-lookup"><span data-stu-id="a7f54-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="a7f54-148">Du kan använda `X` åtgärden för att förbereda statusarna i formatet $ \ket{s_0 s_1 \dots s_n} $ för viss klassisk bit-sträng $s $:</span><span class="sxs-lookup"><span data-stu-id="a7f54-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="a7f54-149">Senare visas fler kompakta sätt att skriva den här åtgärden som inte kräver manuellt kontroll flöde.</span><span class="sxs-lookup"><span data-stu-id="a7f54-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="a7f54-150">Du kan också förbereda tillstånd som $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ och $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ genom att använda Hadamard Transform $H $, som representeras Q# av den inre åtgärden [`H`](xref:microsoft.quantum.intrinsic.h) (även av typen (qubit => Unit rejust + CTL) '):</span><span class="sxs-lookup"><span data-stu-id="a7f54-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

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

## <a name="measurements"></a><span data-ttu-id="a7f54-151">Mått</span><span class="sxs-lookup"><span data-stu-id="a7f54-151">Measurements</span></span>

<span data-ttu-id="a7f54-152">Mätningar av enskilda qubits kan utföras i olika baser, varje representeras av en Pauli-axel på [Bloch-sfären](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="a7f54-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="a7f54-153">*Beräknings basen* avser `PauliZ` basen och är den vanligaste användnings punkten för mått.</span><span class="sxs-lookup"><span data-stu-id="a7f54-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="a7f54-154">Mäta en enskild qubit baserat på `PauliZ`</span><span class="sxs-lookup"><span data-stu-id="a7f54-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="a7f54-155">Använd [`M`](xref:microsoft.quantum.intrinsic.m) åtgärden, som är en inbyggd icke-enhetlig drift, för att mäta en enskild qubit i `PauliZ` grunden och tilldela ett klassiskt värde till resultatet.</span><span class="sxs-lookup"><span data-stu-id="a7f54-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="a7f54-156">`M`har en reserverad returtyp, `Result` som endast kan ta värden `Zero` eller `One` som motsvarar de uppmätta tillstånden $ \ket {0} $ eller $ \ket {1} $ – vilket indikerar att resultatet inte längre är ett Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a7f54-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="a7f54-157">Ett enkelt exempel är följande åtgärd, som allokerar en qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet på grund av detta `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="a7f54-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="a7f54-158">Mät en eller flera qubits i vissa baser</span><span class="sxs-lookup"><span data-stu-id="a7f54-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="a7f54-159">Om du vill mäta en matris med en eller flera qubits i vissa baser kan du använda [`Measure`](xref:microsoft.quantum.intrinsic.measure) åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a7f54-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="a7f54-160">Indatan till `Measure` är en matris med `Pauli` typer (till exempel `[PauliX, PauliZ, PauliZ]` ) och en matris med qubits.</span><span class="sxs-lookup"><span data-stu-id="a7f54-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="a7f54-161">Ett något mer komplicerat exempel ges av följande åtgärd, som returnerar det booleska värdet `true` om alla qubits i ett register av typen `Qubit[]` är i läget noll när de mäts i en angiven Pauli och som returnerar `false` annars.</span><span class="sxs-lookup"><span data-stu-id="a7f54-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="a7f54-162">Observera att det här exemplet fortfarande bara utför `Measure` en enskild qubits i taget, men åtgärden kan utökas till gemensamma mått på flera qubits.</span><span class="sxs-lookup"><span data-stu-id="a7f54-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="a7f54-163">Exempel på upplåning av qubits</span><span class="sxs-lookup"><span data-stu-id="a7f54-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="a7f54-164">Det finns exempel i Canon som använder `borrowing` nyckelordet, till exempel följande funktion `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="a7f54-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="a7f54-165">Om anger `controls` vilka kontroll-qubits som ska läggas till i en `X` åtgärd är antalet [ancillas](xref:microsoft.quantum.glossary#ancilla) som har lagts till av den här implementeringen `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="a7f54-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="a7f54-166">Observera att det här exemplet använde en omfattande användning av `With` Combinator, i dess form som är tillämpligt för åtgärder som stöder angränsande, t. ex `WithA` ..</span><span class="sxs-lookup"><span data-stu-id="a7f54-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="a7f54-167">Det här är ett användbart programmerings format eftersom du lägger till kontrollen till strukturer som `With` endast sprider kontroll till den inre åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a7f54-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="a7f54-168">Observera också att `body` en implementering av `controlled` Åtgärds innehållet uttryckligen tillhandahölls, förutom för åtgärden, i stället för att skicka en `controlled auto` instruktion.</span><span class="sxs-lookup"><span data-stu-id="a7f54-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="a7f54-169">Orsaken till detta är att på grund av krets strukturen, är det enkelt att lägga till ytterligare kontroller, vilket är fördelaktigt jämfört med att lägga till kontrollen i varje grind i `body` .</span><span class="sxs-lookup"><span data-stu-id="a7f54-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="a7f54-170">Det är en instruktion att jämföra den här koden med en annan Canon `MultiControlledXClean` -funktion som uppnår samma mål för att implementera en multiplicering-kontrollerad `X` åtgärd, men som använder flera rena qubits med `using` mekanismen.</span><span class="sxs-lookup"><span data-stu-id="a7f54-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a7f54-171">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a7f54-171">Next steps</span></span>

<span data-ttu-id="a7f54-172">Lär dig mer om [kontroll flöde](xref:microsoft.quantum.guide.controlflow) i Q# .</span><span class="sxs-lookup"><span data-stu-id="a7f54-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>