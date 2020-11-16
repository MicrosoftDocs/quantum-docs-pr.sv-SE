---
title: 'Variabler i Q#'
description: 'Lär dig hur du arbetar med olika variabler i Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 67c71c09e004d77360902360fefc7a7752e4a829
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690933"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="539ec-103">Variabler i Q#</span><span class="sxs-lookup"><span data-stu-id="539ec-103">Variables in Q#</span></span>

<span data-ttu-id="539ec-104">Q# särskiljer mellan föränderligt och oföränderliga symboler, eller *variabler* , som är kopplade/tilldelade till uttryck.</span><span class="sxs-lookup"><span data-stu-id="539ec-104">Q# distinguishes between mutable and immutable symbols, or *variables* , which are bound/assigned to expressions.</span></span>
<span data-ttu-id="539ec-105">I allmänhet uppmuntras användningen av oföränderliga symboler eftersom den tillåter kompilatorn att utföra mer optimeringar.</span><span class="sxs-lookup"><span data-stu-id="539ec-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="539ec-106">Den vänstra sidan av en bindning består av en symbol tupel och högra sidan av ett uttryck.</span><span class="sxs-lookup"><span data-stu-id="539ec-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="539ec-107">Variabler som inte är oföränderlig</span><span class="sxs-lookup"><span data-stu-id="539ec-107">Immutable Variables</span></span>

<span data-ttu-id="539ec-108">Du kan tilldela ett värde av vilken typ som helst i Q# en variabel för åter användning i en åtgärd eller funktion med hjälp av `let` nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="539ec-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="539ec-109">En oföränderlig bindning består av nyckelordet `let` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda symbolerna till och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="539ec-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="539ec-110">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="539ec-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="539ec-111">Detta tilldelar en viss matris av Pauli-operatörer till variabel namnet (eller symbol) `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="539ec-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="539ec-112">I föregående exempel behöver du inte uttryckligen ange typen för den nya variabeln, eftersom uttrycket till höger i `let` instruktionen är entydigt, och kompilatorn härleder rätt typ.</span><span class="sxs-lookup"><span data-stu-id="539ec-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="539ec-113">Variabler som definieras med `let` är *oföränderliga* , vilket innebär att du inte längre kan ändra det när du har definierat det.</span><span class="sxs-lookup"><span data-stu-id="539ec-113">Variables defined using `let` are *immutable* , meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="539ec-114">Detta möjliggör flera betalnings optimeringar, inklusive optimering av den klassiska logiken som används i variabler för att sorteras om för att tillämpa `Adjoint` en åtgärds variant.</span><span class="sxs-lookup"><span data-stu-id="539ec-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="539ec-115">Föränderligt-variabler</span><span class="sxs-lookup"><span data-stu-id="539ec-115">Mutable Variables</span></span>

<span data-ttu-id="539ec-116">Som ett alternativ till att skapa en variabel med `let` , `mutable` skapar nyckelordet en föränderligt-variabel som *kan* bindas om när den ursprungligen har skapats med hjälp av `set` nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="539ec-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="539ec-117">Du kan binda om symboler som har deklarerats och bundits som en del av en `mutable` instruktion till ett annat värde senare i koden.</span><span class="sxs-lookup"><span data-stu-id="539ec-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="539ec-118">Om en symbol har bundits igen senare i koden, ändras inte dess typ och det nya gräns värdet måste vara kompatibelt med den typen.</span><span class="sxs-lookup"><span data-stu-id="539ec-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="539ec-119">OMBINDNING av föränderligt symboler</span><span class="sxs-lookup"><span data-stu-id="539ec-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="539ec-120">Du kan binda om en föränderligt-variabel med hjälp av en `set` instruktion.</span><span class="sxs-lookup"><span data-stu-id="539ec-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="539ec-121">En sådan OMBINDNING består av nyckelordet `set` följt av en symbol-eller Symbols tupel, ett likhets tecken `=` , ett uttryck för att binda om symbolerna till och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="539ec-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="539ec-122">Här följer några exempel på OMBINDNING av instruktions tekniker.</span><span class="sxs-lookup"><span data-stu-id="539ec-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="539ec-123">Uttryck för Apply-och-Reassign</span><span class="sxs-lookup"><span data-stu-id="539ec-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="539ec-124">En särskild typ av `set` sats, uttrycket *Apply-och-Reassign* , är ett bekvämt sätt att sammanfoga om den högra sidan består av en binär Operators program, och resultatet måste bindas till det vänstra argumentet till operatorn.</span><span class="sxs-lookup"><span data-stu-id="539ec-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="539ec-125">Exempel:</span><span class="sxs-lookup"><span data-stu-id="539ec-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="539ec-126">ökar värdet för räknaren `counter` i varje iteration av `for` slingan.</span><span class="sxs-lookup"><span data-stu-id="539ec-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="539ec-127">Föregående kod motsvarar</span><span class="sxs-lookup"><span data-stu-id="539ec-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="539ec-128">Liknande instruktioner är tillgängliga för alla binära operatorer där typen för den vänstra sidan matchar uttrycks typen.</span><span class="sxs-lookup"><span data-stu-id="539ec-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="539ec-129">Dessa uttryck ger ett bekvämt sätt att ackumulera värden.</span><span class="sxs-lookup"><span data-stu-id="539ec-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="539ec-130">Till exempel är supposing `qubits` ett register över qubits:</span><span class="sxs-lookup"><span data-stu-id="539ec-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="539ec-131">Instruktioner för uppdatering och omtilldelning</span><span class="sxs-lookup"><span data-stu-id="539ec-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="539ec-132">Det finns en liknande sammanfogning för [kopierings-och uppdaterings uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) på den högra sidan.</span><span class="sxs-lookup"><span data-stu-id="539ec-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="539ec-133">Det finns ett uttryck för *uppdatering och omtilldelning* för *namngivna objekt* i användardefinierade typer samt för *mat ris objekt* .</span><span class="sxs-lookup"><span data-stu-id="539ec-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items* .</span></span>  

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

<span data-ttu-id="539ec-134">Om det finns matriser [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) Q# innehåller standard biblioteket de verktyg som krävs för många vanliga behov av initiering och manipulering av matris, och därför kan du undvika att behöva uppdatera mat ris objekt på den första platsen.</span><span class="sxs-lookup"><span data-stu-id="539ec-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="539ec-135">Uppdaterings-och omtilldelnings instruktioner ger ett alternativ om det behövs:</span><span class="sxs-lookup"><span data-stu-id="539ec-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="539ec-136">Med hjälp av biblioteks verktygen för matriser som finns i [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) , kan du till exempel enkelt definiera en funktion som returnerar en matris med `Pauli` typer där elementet i indexet `i` tar ett givet `Pauli` värde, och alla andra poster är identiteten ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="539ec-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="539ec-137">Här följer två definitioner av en sådan funktion, med den andra som drar nytta av verktygen i vårt förfogande.</span><span class="sxs-lookup"><span data-stu-id="539ec-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

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

<span data-ttu-id="539ec-138">I stället för att iterera över varje index i matrisen och villkorligt ange det till `PauliI` eller angivet `pauli` , kan du i stället använda `ConstantArray` från [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) för att skapa en mat ris `PauliI` typ och sedan bara returnera ett kopierings-och-uppdatera-uttryck där du har ändrat det aktuella värdet vid indexet `location` :</span><span class="sxs-lookup"><span data-stu-id="539ec-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="539ec-139">Tupel och avkonstruktion</span><span class="sxs-lookup"><span data-stu-id="539ec-139">Tuple Deconstruction</span></span>

<span data-ttu-id="539ec-140">Förutom att tilldela en enskild variabel kan du använda `let` nyckelorden och, `mutable` eller någon annan bindnings konstruktion, till exempel `set` för att packa upp innehållet i en tuple- [typ](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="539ec-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="539ec-141">En tilldelning av det här formuläret är att *avkonstruera* elementen i denna tupel.</span><span class="sxs-lookup"><span data-stu-id="539ec-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="539ec-142">Om bindningens högra sida är en tupel kan du dekonstruera denna tupel vid tilldelning.</span><span class="sxs-lookup"><span data-stu-id="539ec-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="539ec-143">Sådana dekonstruktioner kan omfatta kapslade tupler och all fullständig eller delvis inbyggnad är giltig så länge formen på tuppeln på den högra sidan är kompatibel med symbolens tuple-form.</span><span class="sxs-lookup"><span data-stu-id="539ec-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="539ec-144">Exempel:</span><span class="sxs-lookup"><span data-stu-id="539ec-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="539ec-145">Bindnings omfång</span><span class="sxs-lookup"><span data-stu-id="539ec-145">Binding Scopes</span></span>

<span data-ttu-id="539ec-146">I allmänhet ligger symbol bindningar utanför definitions området och blir instabil i slutet av uttrycks blocket som de inträffar i.</span><span class="sxs-lookup"><span data-stu-id="539ec-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="539ec-147">Det finns två undantag till den här regeln:</span><span class="sxs-lookup"><span data-stu-id="539ec-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="539ec-148">Bindningen för loop-variabeln i en `for` slinga är inom omfånget för for-slingan, men inte efter slutet av slingan.</span><span class="sxs-lookup"><span data-stu-id="539ec-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="539ec-149">Alla tre delarna i en `repeat` / `until` slinga (bröd texten, testet och korrigeringen) fungerar som ett enda omfång, så symboler som är kopplade till bröd texten är tillgängliga i testet och korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="539ec-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="539ec-150">För båda typerna av slingor körs varje pass genom slingan i sin egen omfattning, så bindningar från ett tidigare pass är inte tillgängliga i ett senare pass.</span><span class="sxs-lookup"><span data-stu-id="539ec-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="539ec-151">Mer information om dessa slingor finns i [kontroll flöde](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="539ec-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="539ec-152">Inre block ärver symbol bindningar från yttre block.</span><span class="sxs-lookup"><span data-stu-id="539ec-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="539ec-153">Du kan bara binda en symbol en gång per block. Det är inte tillåtet att definiera en symbol med samma namn som en annan symbol inom omfånget (ingen "skuggning").</span><span class="sxs-lookup"><span data-stu-id="539ec-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="539ec-154">Följande sekvenser är juridiska:</span><span class="sxs-lookup"><span data-stu-id="539ec-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="539ec-155">och</span><span class="sxs-lookup"><span data-stu-id="539ec-155">and</span></span>

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

<span data-ttu-id="539ec-156">Men detta skulle vara ogiltigt:</span><span class="sxs-lookup"><span data-stu-id="539ec-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="539ec-157">som skulle:</span><span class="sxs-lookup"><span data-stu-id="539ec-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="539ec-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="539ec-158">Next steps</span></span>

<span data-ttu-id="539ec-159">Lär dig mer om att [arbeta med qubits](xref:microsoft.quantum.guide.qubits) i Q# .</span><span class="sxs-lookup"><span data-stu-id="539ec-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>