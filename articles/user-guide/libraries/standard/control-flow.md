---
title: 'Flödes kontroller i :::no-loc(Q#)::: standard libararies'
description: 'Lär dig mer om flödes kontroll åtgärder och funktioner i Microsoft :::no-loc(Q#)::: standard-biblioteket.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: ad107f5c65a4bf368d12d30e4a72786f2076205c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690864"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="3b016-103">Higher-Order kontroll flöde</span><span class="sxs-lookup"><span data-stu-id="3b016-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="3b016-104">En av de primära rollerna i standard biblioteket är att göra det enklare att uttrycka algoritmiska idéer på hög nivå som [Quantum-program](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="3b016-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="3b016-105">:::no-loc(Q#):::Canon tillhandahåller därför en mängd olika konstruktioner för flödes kontroll, som var och en implementeras med hjälp av delvis tillämpning av funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3b016-105">Thus, the :::no-loc(Q#)::: canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="3b016-106">Hoppa direkt till ett exempel, Tänk på i vilket fall ett som vill skapa en "CNOT-steg" i ett register:</span><span class="sxs-lookup"><span data-stu-id="3b016-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="3b016-107">Vi kan uttrycka det här mönstret genom att använda iterationer och `for` slingor:</span><span class="sxs-lookup"><span data-stu-id="3b016-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="3b016-108">Uttryckt i form av <xref:Microsoft.Quantum.Canon.ApplyToEachCA> och mat ris manipulations funktioner, till exempel, <xref:Microsoft.Quantum.Arrays.Zipped> är det mycket kortare och lättare att läsa:</span><span class="sxs-lookup"><span data-stu-id="3b016-108">Expressed in terms of <xref:Microsoft.Quantum.Canon.ApplyToEachCA> and array manipulation functions such as <xref:Microsoft.Quantum.Arrays.Zipped>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="3b016-109">I resten av det här avsnittet kommer vi att tillhandahålla ett antal exempel på hur du använder de olika flödes styrnings åtgärder och-funktioner som tillhandahålls av Canon för att komprimera Express Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="3b016-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="3b016-110">Använda åtgärder och funktioner över matriser och intervall</span><span class="sxs-lookup"><span data-stu-id="3b016-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="3b016-111">En av de primära abstraktionerna från Canon är den iterationen.</span><span class="sxs-lookup"><span data-stu-id="3b016-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="3b016-112">Anta till exempel att du har en enhetlig utformning av formuläret $U \otimes U \otimes \cdots \otimes U $ för en enda qubit-$U $.</span><span class="sxs-lookup"><span data-stu-id="3b016-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="3b016-113">I kan :::no-loc(Q#)::: vi använda <xref:Microsoft.Quantum.Arrays.IndexRange> för att representera detta som en `for` slinga över ett register:</span><span class="sxs-lookup"><span data-stu-id="3b016-113">In :::no-loc(Q#):::, we might use <xref:Microsoft.Quantum.Arrays.IndexRange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="3b016-114">Vi kan sedan använda den nya åtgärden som `HAll(register)` att tillämpa $H \Otimes h \otimes \cdots \Otimes h $.</span><span class="sxs-lookup"><span data-stu-id="3b016-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="3b016-115">Detta är besvärligt att göra, särskilt i en större algoritm.</span><span class="sxs-lookup"><span data-stu-id="3b016-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="3b016-116">Den här metoden är dessutom specialiserad på den särskilda åtgärd som vi vill tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="3b016-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="3b016-117">Vi kan använda det faktum att åtgärder är första klass för att uttrycka det här algoritmiska konceptet uttryckligen:</span><span class="sxs-lookup"><span data-stu-id="3b016-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="3b016-118">Här anger suffixet `CA` att anropet till `ApplyToEach` är adjointable och kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="3b016-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="3b016-119">Om `U` stöder `Adjoint` och `Controlled` , är följande rader likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="3b016-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="3b016-120">Det innebär särskilt att anrop till `ApplyToEachCA` kan visas i åtgärder för vilka en angränsande specialisering genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3b016-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="3b016-121">På samma sätt <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> är det bra att representera mönster i formuläret `U(0, targets[0]); U(1, targets[1]); ...` och erbjuder versioner för varje kombination av functors som stöds av indata.</span><span class="sxs-lookup"><span data-stu-id="3b016-121">Similarly, <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="3b016-122">`ApplyToEach` är typ-parameterad så att den kan användas med åtgärder som tar andra indata än `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="3b016-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="3b016-123">Anta till exempel att `codeBlocks` är en matris med <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> värden som behöver återställas.</span><span class="sxs-lookup"><span data-stu-id="3b016-123">For example, suppose that `codeBlocks` is an array of <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> values that need to be recovered.</span></span>
> <span data-ttu-id="3b016-124">Sedan `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` kommer att använda fel korrigerings kod `code` och återställnings funktion `recoveryFn` för varje block oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="3b016-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="3b016-125">Detta omfattar även för klassiska indata: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` en rotation på $ \pi/$2 om $X $ följt av en rotation på $Pi/$3 om $Y $.</span><span class="sxs-lookup"><span data-stu-id="3b016-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="3b016-126">:::no-loc(Q#):::Canon har även stöd för klassiska uppräknings mönster som är bekanta med funktions programmering.</span><span class="sxs-lookup"><span data-stu-id="3b016-126">The :::no-loc(Q#)::: canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="3b016-127">Implementera till exempel <xref:Microsoft.Quantum.Arrays.Fold> mönstret $f (f (f (s \_ {\text{initial}}, x \_ 0), x \_ 1), \dots) $ för att minska en funktion över en lista.</span><span class="sxs-lookup"><span data-stu-id="3b016-127">For instance, <xref:Microsoft.Quantum.Arrays.Fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="3b016-128">Det här mönstret kan användas för att implementera summor, produkter, minimi, maximal och andra funktioner:</span><span class="sxs-lookup"><span data-stu-id="3b016-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="3b016-129">På samma sätt kan funktioner som <xref:Microsoft.Quantum.Arrays.Mapped> och <xref:Microsoft.Quantum.Arrays.MappedByIndex> användas för att uttrycka funktionella programmerings koncept i :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="3b016-129">Similarly, functions like <xref:Microsoft.Quantum.Arrays.Mapped> and <xref:Microsoft.Quantum.Arrays.MappedByIndex> can be used to express functional programming concepts in :::no-loc(Q#):::.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="3b016-130">Skapa åtgärder och funktioner</span><span class="sxs-lookup"><span data-stu-id="3b016-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="3b016-131">De kontroll flödes konstruktioner som tillhandahålls av Canon utför åtgärder och fungerar som indata, så att det är bra att kunna skapa flera åtgärder eller funktioner i ett enda anrop.</span><span class="sxs-lookup"><span data-stu-id="3b016-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="3b016-132">Mönstret $UVU ^ {\dagger} $ är till exempel mycket vanligt i Quantum-programmering, så att Canon tillhandahåller åtgärden <xref:Microsoft.Quantum.Canon.ApplyWith> som en abstraktion för det här mönstret.</span><span class="sxs-lookup"><span data-stu-id="3b016-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:Microsoft.Quantum.Canon.ApplyWith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="3b016-133">Den här abstraktionen gör det också möjligt att effektivt följa kretsar, eftersom det `Controlled` inte behöver vidta några åtgärder på grund av sekvensen `U(qubit); V(qubit); Adjoint U(qubit);` `U` .</span><span class="sxs-lookup"><span data-stu-id="3b016-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="3b016-134">Vi kan se detta genom att låta $c (U) $ vara den enhetliga som representerar `Controlled U([control], target)` och låta $c (V) $ definieras på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="3b016-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="3b016-135">För ett godtyckligt tillstånd $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (uvu ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes u ^ \dagger) \ket {1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="3b016-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="3b016-136">\end{align} enligt definitionen av `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="3b016-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="3b016-137">Å andra sidan, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket \otimes {0} \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (v)) (\boldone \otimes u ^ \dagger) \ket {0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="3b016-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="3b016-138">\end{align} med linjäritet kan vi säga att vi kan räkna $U $ på det här sättet för alla ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="3b016-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="3b016-139">Det vill säga $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="3b016-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="3b016-140">Eftersom styrnings åtgärder kan vara dyra i allmänhet, använder kontrollerade varianter som `WithC` och `WithCA` kan hjälpa till att minska antalet kontroll functors som behöver tillämpas.</span><span class="sxs-lookup"><span data-stu-id="3b016-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="3b016-141">En annan följd av utjämningen $U $ är att vi inte behöver ens veta hur du tillämpar `Controlled` Functor på `U` .</span><span class="sxs-lookup"><span data-stu-id="3b016-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="3b016-142">`ApplyWithCA` har därför en svagare signatur än vad som kan förväntas:</span><span class="sxs-lookup"><span data-stu-id="3b016-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="3b016-143">På samma sätt <xref:Microsoft.Quantum.Canon.Bound> skapar åtgärder som tillämpar en sekvens av andra åtgärder i tur och ordning.</span><span class="sxs-lookup"><span data-stu-id="3b016-143">Similarly, <xref:Microsoft.Quantum.Canon.Bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="3b016-144">Till exempel motsvarar följande:</span><span class="sxs-lookup"><span data-stu-id="3b016-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="3b016-145">Att kombinera med upprepnings mönster kan göra detta särskilt användbart:</span><span class="sxs-lookup"><span data-stu-id="3b016-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="3b016-146">Time-Ordered sammansättning</span><span class="sxs-lookup"><span data-stu-id="3b016-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="3b016-147">Vi kan gå vidare ytterligare genom att tänka på flödes kontroll i termer av partiella program och klassiska funktioner, och kan modellera ännu ganska avancerade Quantum-koncept vad gäller klassisk flödes kontroll.</span><span class="sxs-lookup"><span data-stu-id="3b016-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="3b016-148">Den här analoga delen görs exakt genom igenkänningen att de enhetliga operatörerna motsvarar sidans effekter av anrops åtgärder, till exempel att eventuell nedbrytning av enhetliga operatörer i termer av andra enhetliga operatörer motsvarar att skapa en särskild anrops ordning för klassiska under rutiner som genererar instruktioner för att agera som specifika enhetliga operatörer.</span><span class="sxs-lookup"><span data-stu-id="3b016-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="3b016-149">I den här vyn `Bound` är en exakt representation av mat ris produkten, eftersom `Bound([A, B])(target)` motsvarar `A(target); B(target);` , vilket i sin tur är den anrops ordning som motsvarar $ba $.</span><span class="sxs-lookup"><span data-stu-id="3b016-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="3b016-150">Ett mer avancerat exempel är [Trotter – Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="3b016-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="3b016-151">Som det beskrivs i avsnittet om åter givning av dynamisk Generator i [data strukturer](xref:microsoft.quantum.libraries.data-structures), är Trotter – Suzuki-expansion ett särskilt användbart sätt att uttrycka mat ris exponenter.</span><span class="sxs-lookup"><span data-stu-id="3b016-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="3b016-152">Om du till exempel använder utökningen i den lägsta ordern ger alla operatörer $A $ och $B $ sådana $A = A ^ \dagger $ och $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (in A t/n) \exp (i B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="3b016-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="3b016-153">\end{align} colloquially, vi säger att vi kan ungefär utveckla ett tillstånd under $A + B $ genom en annan utveckling under $A $ och $B $ ensamt.</span><span class="sxs-lookup"><span data-stu-id="3b016-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="3b016-154">Om vi representerar utvecklingen under $A $ med en åtgärd `A : (Double, Qubit[]) => Unit` som gäller $e ^ {i t A} $, blir åter givningen av Trotter – Suzuki-expansionen i termer av att ordna om anrops sekvenser tydlig.</span><span class="sxs-lookup"><span data-stu-id="3b016-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="3b016-155">Konkret, med tanke på en åtgärd `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` som `A = U(0, _, _)` och `B = U(1, _, _)` , kan vi definiera en ny åtgärd som representerar integralen av `U` vid tiden $t $ genom att generera sekvenser av formuläret</span><span class="sxs-lookup"><span data-stu-id="3b016-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="3b016-156">Nu kan vi nu vara orsaken till Trotter – Suzuki-expansionen *utan referens till Quantum Mechanics* .</span><span class="sxs-lookup"><span data-stu-id="3b016-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all* .</span></span>
<span data-ttu-id="3b016-157">Expansionen är i praktiken ett särskilt upprepnings mönster som är motiverat av $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="3b016-158">Detta upprepnings mönster implementeras av <xref:Microsoft.Quantum.Canon.DecomposedIntoTimestepsCA> :</span><span class="sxs-lookup"><span data-stu-id="3b016-158">This iteration pattern is implemented by <xref:Microsoft.Quantum.Canon.DecomposedIntoTimestepsCA>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="3b016-159">Signaturen för `DecomposeIntoTimeStepsCA` följer ett vanligt mönster i :::no-loc(Q#)::: , där samlingar som kan säkerhets kopie ras antingen av matriser eller av något som beräknar element i farten representeras av tupler vars första element är `Int` värden som anger deras längd.</span><span class="sxs-lookup"><span data-stu-id="3b016-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in :::no-loc(Q#):::, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="3b016-160">Placera det tillsammans: styra åtgärder</span><span class="sxs-lookup"><span data-stu-id="3b016-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="3b016-161">Dessutom bygger Canon på `Controlled` Functor genom att tillhandahålla ytterligare sätt att utvärdera Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3b016-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="3b016-162">Det är vanligt, särskilt i Quantum-aritmetiskt, till villkors åtgärder i andra beräknings underlag än $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="3b016-163">Med hjälp av de kontroll åtgärder och funktioner som introducerades ovan kan vi använda mer generella Quantum villkor i ett enda uttryck.</span><span class="sxs-lookup"><span data-stu-id="3b016-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="3b016-164">Nu ska vi gå vidare till hur <xref:Microsoft.Quantum.Canon.ControlledOnBitString> ser det (San-typ parametrar). sedan kommer vi att dela upp delarna en i taget.</span><span class="sxs-lookup"><span data-stu-id="3b016-164">Let's jump in to how <xref:Microsoft.Quantum.Canon.ControlledOnBitString> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="3b016-165">Det första vi behöver göra är att definiera en åtgärd som faktiskt utför den stora avläsningen av genomförandet av kontrollen i godtyckliga beräknings bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="3b016-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="3b016-166">Vi kommer inte att anropa den här åtgärden direkt, men vi lägger till `_` i början av namnet för att ange att det är en implementering av en annan konstruktion någon annan stans.</span><span class="sxs-lookup"><span data-stu-id="3b016-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="3b016-167">Observera att vi tar en sträng med bitar, som visas som en `Bool` matris, som vi använder för att ange det villkor som vi vill tillämpa på den åtgärd `oracle` som vi har fått.</span><span class="sxs-lookup"><span data-stu-id="3b016-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="3b016-168">Eftersom den här åtgärden faktiskt gör programmet direkt, behöver vi också ta kontroll-och mål registren, som båda visas här som `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="3b016-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="3b016-169">Nu noterar vi att du har kontroll över beräknings bas tillstånd $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ för en bit sträng $ \vec{s} $ kan realiseras genom att omvandla $ \ket{\vec{s}} $ till $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="3b016-170">I synnerhet $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="3b016-171">Eftersom $X ^ {\dagger} = X $, innebär detta att $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="3b016-172">Därför kan vi använda $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} $, tillämpa `Controlled oracle` och omvandla tillbaka till $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="3b016-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="3b016-173">Den här konstruktionen är exakt `ApplyWith` , så vi skriver texten i vår nya åtgärd i enlighet med detta:</span><span class="sxs-lookup"><span data-stu-id="3b016-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="3b016-174">Här har vi använt <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> för att tillämpa $P $, som delvis använder sig av målet för användning med `ApplyWith` .</span><span class="sxs-lookup"><span data-stu-id="3b016-174">Here, we have used <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="3b016-175">Observera dock att vi behöver omvandla *kontroll* registret till vårt önskade formulär, så vi använder delvis den inre åtgärden `(Controlled oracle)` på *målet* .</span><span class="sxs-lookup"><span data-stu-id="3b016-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target* .</span></span>
<span data-ttu-id="3b016-176">Detta `ApplyWith` gör att du får en parentes för kontroll registret med $P $, precis som vi vill.</span><span class="sxs-lookup"><span data-stu-id="3b016-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="3b016-177">Vi kan nu vara klara, men det tar på sig att inte uppfylla den nya åtgärden, som att använda `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="3b016-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="3b016-178">Vi slutför därför att definiera vårt nya kontroll flödes koncept genom att skriva en funktion som gör att Oracle kan styras och som returnerar en ny åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3b016-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="3b016-179">På så sätt ser vi till att vår nya funktion ser ut ungefär likadant ut `Controlled` , vilket illustrerar att vi enkelt kan definiera kraftfulla nya styrnings flödes konstruktioner som använder :::no-loc(Q#)::: och Canon tillsammans:</span><span class="sxs-lookup"><span data-stu-id="3b016-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using :::no-loc(Q#)::: and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
