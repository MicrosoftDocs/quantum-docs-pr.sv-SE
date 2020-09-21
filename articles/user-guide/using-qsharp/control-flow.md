---
title: Kontroll flöde i Q#
description: Slingor, villkor osv.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8c873868d6f697fc90b23a38c11f35e46b40c4f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759670"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="3dd33-103">Kontroll flöde i Q#</span><span class="sxs-lookup"><span data-stu-id="3dd33-103">Control flow in Q#</span></span>

<span data-ttu-id="3dd33-104">I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som andra vanliga tvingande klassiska språk.</span><span class="sxs-lookup"><span data-stu-id="3dd33-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="3dd33-105">Du kan dock ändra kontroll flödet på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="3dd33-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="3dd33-106">`if` instruktioner</span><span class="sxs-lookup"><span data-stu-id="3dd33-106">`if` statements</span></span>
* <span data-ttu-id="3dd33-107">`for` slingor</span><span class="sxs-lookup"><span data-stu-id="3dd33-107">`for` loops</span></span>
* <span data-ttu-id="3dd33-108">`repeat-until-success` slingor</span><span class="sxs-lookup"><span data-stu-id="3dd33-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="3dd33-109">`if` `for` Konstruktionerna för och kontroll flödet fortsätter att vara bekanta med de flesta klassiska programmeringsspråk.</span><span class="sxs-lookup"><span data-stu-id="3dd33-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="3dd33-110">[`Repeat-until-success`](#repeat-until-success-loop) slingor beskrivs längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="3dd33-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="3dd33-111">Det är viktigt `for` att du använder slingor och `if` uttryck i åtgärder för vilka [specialisering](xref:microsoft.quantum.guide.operationsfunctions) genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3dd33-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="3dd33-112">I det scenariot kastar det intilliggande av en `for` slinga riktningen och tar det angränsande av varje iteration.</span><span class="sxs-lookup"><span data-stu-id="3dd33-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="3dd33-113">Den här åtgärden följer principen "skor-och-SOCKS": om du vill ångra att sätta igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS.</span><span class="sxs-lookup"><span data-stu-id="3dd33-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="3dd33-114">Om, annars, annars</span><span class="sxs-lookup"><span data-stu-id="3dd33-114">If, Else-if, Else</span></span>

<span data-ttu-id="3dd33-115">`if`Instruktionen stöder villkorlig körning.</span><span class="sxs-lookup"><span data-stu-id="3dd33-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="3dd33-116">Det består av nyckelordet `if` , ett booleskt uttryck inom parentes och ett instruktions block ( _then_ -blocket).</span><span class="sxs-lookup"><span data-stu-id="3dd33-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="3dd33-117">Valfritt antal Else-If-satser kan följa, var och en består av nyckelordet `elif` , ett booleskt uttryck inom parentes och ett instruktions block ( _Else-If-_ block).</span><span class="sxs-lookup"><span data-stu-id="3dd33-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="3dd33-118">Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).</span><span class="sxs-lookup"><span data-stu-id="3dd33-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="3dd33-119">`if`Villkoret utvärderas och om det är *Sant*körs blocket. *then*</span><span class="sxs-lookup"><span data-stu-id="3dd33-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="3dd33-120">Om villkoret är *falskt*utvärderas det första Else-If-villkoret. om detta är sant körs *Else-If-* blocket.</span><span class="sxs-lookup"><span data-stu-id="3dd33-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="3dd33-121">Annars utvärderar det andra-IF-blocket och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.</span><span class="sxs-lookup"><span data-stu-id="3dd33-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="3dd33-122">Om det ursprungliga *IF* -villkoret och alla Else-If-satserna evalueras till *false*körs *Else* -blocket om det anges.</span><span class="sxs-lookup"><span data-stu-id="3dd33-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="3dd33-123">Observera att det körs på det egna omfånget.</span><span class="sxs-lookup"><span data-stu-id="3dd33-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="3dd33-124">Bindningar som görs inuti ett `if` , `elif` eller- `else` block visas inte när blocket slutar.</span><span class="sxs-lookup"><span data-stu-id="3dd33-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="3dd33-125">Exempel:</span><span class="sxs-lookup"><span data-stu-id="3dd33-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="3dd33-126">eller</span><span class="sxs-lookup"><span data-stu-id="3dd33-126">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="3dd33-127">For-loop</span><span class="sxs-lookup"><span data-stu-id="3dd33-127">For loop</span></span>

<span data-ttu-id="3dd33-128">`for`Instruktionen stöder iteration över ett heltals intervall eller en matris.</span><span class="sxs-lookup"><span data-stu-id="3dd33-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="3dd33-129">Instruktionen består av nyckelordet `for` följt av en symbol-eller symbol-tupel, nyckelordet `in` och ett uttryck av typen `Range` eller matris, allt inom parentes och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="3dd33-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="3dd33-130">Instruktions blocket (bröd texten i slingan) körs flera gånger, med den definierade symbolen (loop-variabeln) kopplad till varje värde i intervallet eller matrisen.</span><span class="sxs-lookup"><span data-stu-id="3dd33-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="3dd33-131">Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.</span><span class="sxs-lookup"><span data-stu-id="3dd33-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="3dd33-132">Uttrycket utvärderas fullständigt innan loopen inleds, och ändras inte när loopen körs.</span><span class="sxs-lookup"><span data-stu-id="3dd33-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="3dd33-133">Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.</span><span class="sxs-lookup"><span data-stu-id="3dd33-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="3dd33-134">Loop-variabeln är inte kopplad efter att for-slingan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="3dd33-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="3dd33-135">Bindningen för sling-variabeln är oföränderlig och följer samma regler som andra variabel bindningar.</span><span class="sxs-lookup"><span data-stu-id="3dd33-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="3dd33-136">I de här exemplen `qubits` är ett register över qubits (t. ex. typ `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="3dd33-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="3dd33-137">Observera att vi i slutet använder den aritmetiska operatorn Shift-vänstra binära operatorn `<<<` .</span><span class="sxs-lookup"><span data-stu-id="3dd33-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="3dd33-138">Mer information finns i [numeriska uttryck](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="3dd33-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="3dd33-139">Upprepa-tills-lyckad-slinga</span><span class="sxs-lookup"><span data-stu-id="3dd33-139">Repeat-until-success loop</span></span>

<span data-ttu-id="3dd33-140">Q#Språket tillåter att klassiskt kontroll flöde är beroende av resultatet av att mäta qubits.</span><span class="sxs-lookup"><span data-stu-id="3dd33-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="3dd33-141">Med den här funktionen aktive ras implementera kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.</span><span class="sxs-lookup"><span data-stu-id="3dd33-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="3dd33-142">Exempel på detta är ru: er-mönster ( *REPEAT-until-lyckat* ) i Q# .</span><span class="sxs-lookup"><span data-stu-id="3dd33-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="3dd33-143">Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar. kostnaden beror på den faktiska körningen och Interfoliering av flera möjliga grenar.</span><span class="sxs-lookup"><span data-stu-id="3dd33-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="3dd33-144">För att under lätta upprepade tills klart (ru: er) mönster, Q# stöder konstruktioner</span><span class="sxs-lookup"><span data-stu-id="3dd33-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="3dd33-145">var `expression` är ett giltigt uttryck som utvärderas till ett värde av typen `Bool` .</span><span class="sxs-lookup"><span data-stu-id="3dd33-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="3dd33-146">Loop-texten körs och sedan utvärderas villkoret.</span><span class="sxs-lookup"><span data-stu-id="3dd33-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="3dd33-147">Om villkoret är sant slutförs instruktionen. annars körs korrigeringen och instruktionen körs igen, från och med loop-texten.</span><span class="sxs-lookup"><span data-stu-id="3dd33-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="3dd33-148">Alla tre delar av en ru: er-slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång *för varje upprepning*, så symboler som är kopplade till innehållet är tillgängliga i både testet och korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="3dd33-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="3dd33-149">Att slutföra körningen av korrigeringen avslutar dock omfånget för instruktionen, så att symbol bindningar som görs under bröd texten eller korrigeringen inte är tillgängliga i efterföljande upprepningar.</span><span class="sxs-lookup"><span data-stu-id="3dd33-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="3dd33-150">Vidare `fixup` är uttrycket ofta användbart men inte alltid nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="3dd33-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="3dd33-151">I fall där det inte behövs, konstruktionen</span><span class="sxs-lookup"><span data-stu-id="3dd33-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="3dd33-152">är också ett giltigt ru: er-mönster.</span><span class="sxs-lookup"><span data-stu-id="3dd33-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="3dd33-153">Fler exempel och mer information finns i [Upprepa-till-Slutför-exempel](#repeat-until-success-examples) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="3dd33-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="3dd33-154">Undvik att använda repetitions-till-Slutför-slingor inuti functions.</span><span class="sxs-lookup"><span data-stu-id="3dd33-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="3dd33-155">Använd *while* -slingor för att tillhandahålla motsvarande funktioner i functions.</span><span class="sxs-lookup"><span data-stu-id="3dd33-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="3dd33-156">While-loop</span><span class="sxs-lookup"><span data-stu-id="3dd33-156">While loop</span></span>

<span data-ttu-id="3dd33-157">Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation.</span><span class="sxs-lookup"><span data-stu-id="3dd33-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="3dd33-158">De används ofta i vissa klasser av Quantum-algoritmer – därför den dedikerade språk konstruktionen i Q# .</span><span class="sxs-lookup"><span data-stu-id="3dd33-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="3dd33-159">Loopar som bryts baserat på ett villkor och vars körnings längd är således okänd vid kompileringen, hanteras dock med särskild försiktighet i en Quantum-körning.</span><span class="sxs-lookup"><span data-stu-id="3dd33-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="3dd33-160">Användningen i functions är dock inte problematisk eftersom dessa slingor bara innehåller kod som körs på konventionell (icke-Quantum) maskin vara.</span><span class="sxs-lookup"><span data-stu-id="3dd33-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="3dd33-161">Q#stöder därför endast användningen av while-slingor i functions.</span><span class="sxs-lookup"><span data-stu-id="3dd33-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="3dd33-162">En `while` instruktion består av nyckelordet `while` , ett booleskt uttryck inom parentes och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="3dd33-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="3dd33-163">Instruktions blocket (bröd texten i slingan) körs så länge villkoret utvärderas till `true` .</span><span class="sxs-lookup"><span data-stu-id="3dd33-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="3dd33-164">Return-instruktion</span><span class="sxs-lookup"><span data-stu-id="3dd33-164">Return Statement</span></span>

<span data-ttu-id="3dd33-165">Return-instruktionen avslutar körningen av en åtgärd eller funktion och returnerar ett värde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="3dd33-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="3dd33-166">Det består av nyckelordet `return` följt av ett uttryck av lämplig typ och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="3dd33-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="3dd33-167">Exempel:</span><span class="sxs-lookup"><span data-stu-id="3dd33-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="3dd33-168">eller</span><span class="sxs-lookup"><span data-stu-id="3dd33-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="3dd33-169">Ett anrop som returnerar en tom tupel, `()` kräver ingen Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="3dd33-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="3dd33-170">Om du vill ange en tidig utträde från åtgärden eller funktionen använder du `return ();` .</span><span class="sxs-lookup"><span data-stu-id="3dd33-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="3dd33-171">Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="3dd33-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="3dd33-172">Det finns inget maximalt antal retur uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3dd33-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="3dd33-173">Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="3dd33-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="3dd33-174">Instruktionen misslyckande</span><span class="sxs-lookup"><span data-stu-id="3dd33-174">Fail statement</span></span>

<span data-ttu-id="3dd33-175">Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="3dd33-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="3dd33-176">Det består av nyckelordet `fail` följt av en sträng och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="3dd33-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="3dd33-177">Instruktionen returnerar strängen till den klassiska driv rutinen som fel meddelande.</span><span class="sxs-lookup"><span data-stu-id="3dd33-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="3dd33-178">Det finns ingen begränsning för antalet misslyckande uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3dd33-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="3dd33-179">Kompilatorn kan generera en varning om instruktioner följer en felaktig instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="3dd33-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="3dd33-180">Exempel:</span><span class="sxs-lookup"><span data-stu-id="3dd33-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="3dd33-181">eller, med hjälp av [interpolerade strängar](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="3dd33-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="3dd33-182">Upprepa-till-Slutför-exempel</span><span class="sxs-lookup"><span data-stu-id="3dd33-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="3dd33-183">RU: er-mönster för en qubit rotation om en onormal axel</span><span class="sxs-lookup"><span data-stu-id="3dd33-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="3dd33-184">I ett vanligt användnings fall Q# implementerar följande åtgärd en rotation runt en onormal axel om $ (i + 2i Z)/\sqrt {5} $ på Bloch-sfären.</span><span class="sxs-lookup"><span data-stu-id="3dd33-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="3dd33-185">Implementeringen använder ett känt ru: er-mönster:</span><span class="sxs-lookup"><span data-stu-id="3dd33-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="3dd33-186">RU: er-slinga med en föränderligt-variabel i omfånget</span><span class="sxs-lookup"><span data-stu-id="3dd33-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="3dd33-187">I det här exemplet visas användningen av en föränderligt-variabel, `finished` som ligger inom omfånget för hela upprepnings-tills-korrigering-loopen och som initieras före loopen och uppdateras i korrigerings steget.</span><span class="sxs-lookup"><span data-stu-id="3dd33-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="3dd33-188">RU: er utan `fixup`</span><span class="sxs-lookup"><span data-stu-id="3dd33-188">RUS without `fixup`</span></span>

<span data-ttu-id="3dd33-189">I det här exemplet visas en ru: er-slinga utan korrigerings steget.</span><span class="sxs-lookup"><span data-stu-id="3dd33-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="3dd33-190">Koden är en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ med hjälp av `H` och- `T` grindarna.</span><span class="sxs-lookup"><span data-stu-id="3dd33-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="3dd33-191">Slingan slutar i $ \frac {8} {5} $-upprepningar i genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="3dd33-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="3dd33-192">Se [*REPEAT-until-lyckades: icke-deterministisk dekomposition av Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick och Svore, 2014) för mer information.</span><span class="sxs-lookup"><span data-stu-id="3dd33-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="3dd33-193">RU: er för att förbereda ett Quantum-tillstånd</span><span class="sxs-lookup"><span data-stu-id="3dd33-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="3dd33-194">Slutligen är det ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, med början från $ \ket{+} $ State.</span><span class="sxs-lookup"><span data-stu-id="3dd33-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="3dd33-195">Viktiga programmerings funktioner som visas i den här åtgärden är:</span><span class="sxs-lookup"><span data-stu-id="3dd33-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="3dd33-196">En mer komplex `fixup` del av slingan, som inbegriper Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3dd33-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="3dd33-197">Användning av `AssertMeasurementProbability` instruktioner för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.</span><span class="sxs-lookup"><span data-stu-id="3dd33-197">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="3dd33-198">Mer information om [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) -och-åtgärder finns i [testa och felsöka](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="3dd33-198">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

<span data-ttu-id="3dd33-199">Mer information finns i avsnittet [om enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="3dd33-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dd33-200">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3dd33-200">Next steps</span></span>

<span data-ttu-id="3dd33-201">Lär dig mer om att [testa och felsöka](xref:microsoft.quantum.guide.testingdebugging) i Q# .</span><span class="sxs-lookup"><span data-stu-id="3dd33-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
