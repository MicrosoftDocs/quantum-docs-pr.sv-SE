---
title: 'Kontroll flöde i Q #'
description: Slingor, villkor osv.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326548"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="9a256-103">Kontroll flöde i Q #</span><span class="sxs-lookup"><span data-stu-id="9a256-103">Control Flow in Q#</span></span>

<span data-ttu-id="9a256-104">I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som de flesta vanliga tvingande klassiska språk.</span><span class="sxs-lookup"><span data-stu-id="9a256-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="9a256-105">Det här kontroll flödet kan ändras, men på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="9a256-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="9a256-106">`if`instruktioner</span><span class="sxs-lookup"><span data-stu-id="9a256-106">`if` statements</span></span>
- <span data-ttu-id="9a256-107">`for`slingor</span><span class="sxs-lookup"><span data-stu-id="9a256-107">`for` loops</span></span>
- <span data-ttu-id="9a256-108">`repeat`-`until`slingor</span><span class="sxs-lookup"><span data-stu-id="9a256-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="9a256-109">Vi skjuter upp diskussionen om det [senare.](#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="9a256-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="9a256-110">`if` `for` Kontroll flödes-och kontroll flödes konstruktionerna går dock bra att känna till i de flesta klassiska programmeringsspråk.</span><span class="sxs-lookup"><span data-stu-id="9a256-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="9a256-111">`for`Det är viktigt att slingor och `if` uttryck även kan användas i åtgärder för vilka specialisering genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="9a256-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="9a256-112">I så fall kastar det intilliggande av en `for` slinga riktningen och tar det angränsande av varje iteration.</span><span class="sxs-lookup"><span data-stu-id="9a256-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="9a256-113">Det här följer principen "skor-och-SOCKS": om du vill ångra att du kommer igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS.</span><span class="sxs-lookup"><span data-stu-id="9a256-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="9a256-114">Det fungerar mindre bra om du vill prova och ta din SOCKS medan du fortfarande använder dina skor!</span><span class="sxs-lookup"><span data-stu-id="9a256-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="9a256-115">Om, annars, annars</span><span class="sxs-lookup"><span data-stu-id="9a256-115">If, Else-if, Else</span></span>

<span data-ttu-id="9a256-116">`if`Instruktionen stöder villkorlig körning.</span><span class="sxs-lookup"><span data-stu-id="9a256-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="9a256-117">Det består av nyckelordet `if` , en öppen parentes `(` , ett booleskt uttryck, en avslutande parentes `)` och ett instruktions block ( _then_ -block).</span><span class="sxs-lookup"><span data-stu-id="9a256-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="9a256-118">Detta kan följas av valfri mängd Else-If-satser, som består av nyckelordet `elif` , en öppen parentes `(` , ett booleskt uttryck, en högerparentes `)` och ett instruktions block ( _Else-If-_ block).</span><span class="sxs-lookup"><span data-stu-id="9a256-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="9a256-119">Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).</span><span class="sxs-lookup"><span data-stu-id="9a256-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="9a256-120">`if`Villkoret utvärderas och om det är sant körs blocket.</span><span class="sxs-lookup"><span data-stu-id="9a256-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="9a256-121">Om villkoret är falskt utvärderas det första Else-If-villkoret. om det är sant körs det Else-If-blocket.</span><span class="sxs-lookup"><span data-stu-id="9a256-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="9a256-122">Annars testas det andra-IF-blocket, och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.</span><span class="sxs-lookup"><span data-stu-id="9a256-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="9a256-123">Om det ursprungliga IF-villkoret och alla Else-If-satser utvärderas till false körs Else-blocket om ett har angetts.</span><span class="sxs-lookup"><span data-stu-id="9a256-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="9a256-124">Observera att det körs på det egna omfånget.</span><span class="sxs-lookup"><span data-stu-id="9a256-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="9a256-125">Bindningar som görs inuti ett `if` , `elif` eller- `else` block visas inte efter dess slut.</span><span class="sxs-lookup"><span data-stu-id="9a256-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="9a256-126">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9a256-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="9a256-127">eller</span><span class="sxs-lookup"><span data-stu-id="9a256-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="9a256-128">For-slinga</span><span class="sxs-lookup"><span data-stu-id="9a256-128">For Loop</span></span>

<span data-ttu-id="9a256-129">`for`Instruktionen stöder iteration över ett heltals intervall eller över en matris.</span><span class="sxs-lookup"><span data-stu-id="9a256-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="9a256-130">Instruktionen består av nyckelordet `for` , en öppen parentes `(` följt av en symbol-eller symbol-tupel, nyckelordet `in` , ett uttryck av typen `Range` eller matris, en högerparentes `)` och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="9a256-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="9a256-131">Instruktions blocket (bröd texten i slingan) körs upprepade gånger, med de definierade symbolerna (loop-variabeln) som är kopplade till varje värde i intervallet eller matrisen.</span><span class="sxs-lookup"><span data-stu-id="9a256-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="9a256-132">Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.</span><span class="sxs-lookup"><span data-stu-id="9a256-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="9a256-133">Uttrycket utvärderas fullständigt innan det går in i loopen och ändras inte när slingan körs.</span><span class="sxs-lookup"><span data-stu-id="9a256-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="9a256-134">Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.</span><span class="sxs-lookup"><span data-stu-id="9a256-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="9a256-135">I synnerhet är loop-variabeln inte kopplad efter att for-slingan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9a256-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="9a256-136">Bindningen för de deklarerade symbolerna är oföränderlig och följer samma regler som andra variabel bindningar.</span><span class="sxs-lookup"><span data-stu-id="9a256-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="9a256-137">I vissa exempel är supposing `qubits` ett register över qubits (t. ex. av typ `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="9a256-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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
<span data-ttu-id="9a256-138">Observera att i slutet använder vi den aritmetiska operatorn Shift-vänstra, `<<<` och information om vilka som kan hittas på [numeriska uttryck](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span><span class="sxs-lookup"><span data-stu-id="9a256-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="9a256-139">Upprepa-tills-lyckad-slinga</span><span class="sxs-lookup"><span data-stu-id="9a256-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="9a256-140">Med hjälp av Q #-språket kan ett klassiskt kontroll flöde vara beroende av resultatet av att mäta qubits.</span><span class="sxs-lookup"><span data-stu-id="9a256-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="9a256-141">Den här funktionen aktiverar implementering av kraftfulla Probabilistic-gadgetar som kan minska beräknings kostnaden för att implementera unitaries.</span><span class="sxs-lookup"><span data-stu-id="9a256-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="9a256-142">Som exempel är det enkelt att implementera så kallade ru: er-mönster ( *REPEAT-until-lyckades* ) i Q #.</span><span class="sxs-lookup"><span data-stu-id="9a256-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="9a256-143">Dessa ru: er-mönster är Probabilistic-program som har en *förväntad* låg kostnad i termer av elementära grindar, men för vilka den faktiska kostnaden är beroende av en faktisk körning och en faktisk Interfoliering av olika möjliga grenar.</span><span class="sxs-lookup"><span data-stu-id="9a256-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="9a256-144">Q # stöder konstruktioner för att under lätta upprepningar av ru: er-mönster.</span><span class="sxs-lookup"><span data-stu-id="9a256-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="9a256-145">var `expression` är ett giltigt uttryck som utvärderas till ett värde av typen `Bool` .</span><span class="sxs-lookup"><span data-stu-id="9a256-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="9a256-146">Loop-texten körs och sedan utvärderas villkoret.</span><span class="sxs-lookup"><span data-stu-id="9a256-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="9a256-147">Om villkoret är sant slutförs instruktionen. annars utförs korrigeringen och instruktionen körs igen från och med loop-texten.</span><span class="sxs-lookup"><span data-stu-id="9a256-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="9a256-148">Alla tre delarna av en REPEAT/until-slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång *för varje upprepning*, så symboler som är kopplade till texten är tillgängliga i testet och i korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="9a256-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="9a256-149">Att slutföra körningen av korrigeringen avslutar dock omfånget för instruktionen, så att symbol bindningar som görs under bröd texten eller korrigeringen inte är tillgängliga i efterföljande upprepningar.</span><span class="sxs-lookup"><span data-stu-id="9a256-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="9a256-150">Vidare `fixup` är uttrycket ofta användbart men inte alltid nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="9a256-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="9a256-151">I fall där det inte behövs, konstruktionen</span><span class="sxs-lookup"><span data-stu-id="9a256-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="9a256-152">är också ett giltigt ru: er-mönster.</span><span class="sxs-lookup"><span data-stu-id="9a256-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="9a256-153">Längst ned på sidan presenteras några [exempel på ru: er-slingor](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="9a256-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="9a256-154">Undvik att använda repetitions-till-Slutför-slingor inuti functions.</span><span class="sxs-lookup"><span data-stu-id="9a256-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="9a256-155">Motsvarande funktioner tillhandahålls av while-slingor i functions.</span><span class="sxs-lookup"><span data-stu-id="9a256-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="9a256-156">While-slinga</span><span class="sxs-lookup"><span data-stu-id="9a256-156">While Loop</span></span>

<span data-ttu-id="9a256-157">Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation.</span><span class="sxs-lookup"><span data-stu-id="9a256-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="9a256-158">De används ofta i vissa klasser av Quantum-algoritmer – därför är den dedikerade språk konstruktionen i Q #.</span><span class="sxs-lookup"><span data-stu-id="9a256-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="9a256-159">Loopar som bryts baserat på ett villkor och vars körnings längd alltså är okänd vid kompileringen måste dock hanteras med särskild försiktighet i en Quantum-körning.</span><span class="sxs-lookup"><span data-stu-id="9a256-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="9a256-160">Deras användning i functions å andra sidan är problematisk, eftersom dessa endast innehåller kod som ska köras på konventionell (icke-Quantum) maskin vara.</span><span class="sxs-lookup"><span data-stu-id="9a256-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="9a256-161">Q # stöder därför endast användningen av while-slingor i functions.</span><span class="sxs-lookup"><span data-stu-id="9a256-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="9a256-162">En `while` instruktion består av nyckelordet `while` , en öppen parentes `(` , ett villkor (t. ex. ett booleskt uttryck), en avslutande parentes `)` och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="9a256-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="9a256-163">Instruktions blocket (bröd texten i slingan) körs så länge villkoret utvärderas till `true` .</span><span class="sxs-lookup"><span data-stu-id="9a256-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="9a256-164">Return-instruktion</span><span class="sxs-lookup"><span data-stu-id="9a256-164">Return Statement</span></span>

<span data-ttu-id="9a256-165">Return-instruktionen avslutar körningen av en åtgärd eller funktion och returnerar ett värde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="9a256-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="9a256-166">Det består av nyckelordet `return` följt av ett uttryck av lämplig typ och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="9a256-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="9a256-167">Ett anrop som returnerar en tom tupel, `()` kräver ingen Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="9a256-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="9a256-168">Om en tidig avslutning önskas, `return ()` kan användas i det här fallet.</span><span class="sxs-lookup"><span data-stu-id="9a256-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="9a256-169">Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="9a256-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="9a256-170">Det finns inget maximalt antal retur uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9a256-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="9a256-171">Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="9a256-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="9a256-172">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9a256-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="9a256-173">eller</span><span class="sxs-lookup"><span data-stu-id="9a256-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="9a256-174">eller</span><span class="sxs-lookup"><span data-stu-id="9a256-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="9a256-175">Instruktionen misslyckande</span><span class="sxs-lookup"><span data-stu-id="9a256-175">Fail Statement</span></span>

<span data-ttu-id="9a256-176">Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="9a256-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="9a256-177">Det består av nyckelordet `fail` följt av en sträng och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="9a256-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="9a256-178">Strängen returneras till den klassiska driv rutinen som fel meddelande.</span><span class="sxs-lookup"><span data-stu-id="9a256-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="9a256-179">Det finns ingen begränsning för antalet misslyckande uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9a256-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="9a256-180">Kompilatorn kan generera en varning om instruktioner följer en felaktig instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="9a256-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="9a256-181">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9a256-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="9a256-182">eller, med hjälp av [interpolerade strängar](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="9a256-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="9a256-183">Upprepa-till-Slutför-exempel</span><span class="sxs-lookup"><span data-stu-id="9a256-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="9a256-184">RU: er-mönster för en qubit rotation om en onormal axel</span><span class="sxs-lookup"><span data-stu-id="9a256-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="9a256-185">I ett vanligt användnings fall implementerar följande Q #-åtgärd en rotation runt en onormal axel om $ (I + 2i Z)/\sqrt {5} $ på Bloch-sfären.</span><span class="sxs-lookup"><span data-stu-id="9a256-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="9a256-186">Detta åstadkoms med hjälp av ett känt ru: er-mönster:</span><span class="sxs-lookup"><span data-stu-id="9a256-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="9a256-187">RU: er-slinga med föränderligt-variabel i omfånget</span><span class="sxs-lookup"><span data-stu-id="9a256-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="9a256-188">Det här exemplet visar användningen av en föränderligt-variabel `finished` som ligger inom omfånget för hela upprepnings-till-korrigering-loopen och som initieras före loopen och uppdateras i korrigerings steget.</span><span class="sxs-lookup"><span data-stu-id="9a256-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="9a256-189">RU: er utan`fixup`</span><span class="sxs-lookup"><span data-stu-id="9a256-189">RUS without `fixup`</span></span>

<span data-ttu-id="9a256-190">Följande kod är till exempel en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ med hjälp av- `H` och- `T` grindarna.</span><span class="sxs-lookup"><span data-stu-id="9a256-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="9a256-191">Slingan slutar i $ \frac {8} {5} $-upprepningar i genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="9a256-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="9a256-192">Se [*REPEAT-until-lyckades: icke-deterministisk dekomposition av Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick och Svore, 2014) för mer information.</span><span class="sxs-lookup"><span data-stu-id="9a256-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="9a256-193">RU: er för att förbereda ett Quantum-tillstånd</span><span class="sxs-lookup"><span data-stu-id="9a256-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="9a256-194">Slutligen visar vi ett exempel på ett ru: er-mönster för att förbereda ett Quantum-tillstånd $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, med början från $ \ket{+} $ State.</span><span class="sxs-lookup"><span data-stu-id="9a256-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="9a256-195">Se även [exempel på enhets testning som tillhandahålls med standard biblioteket](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="9a256-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

<span data-ttu-id="9a256-196">Viktiga programmerings funktioner som visas i den här åtgärden är en mer komplex `fixup` del av slingan, vilket inbegriper Quantum-åtgärder och användningen av- `AssertProb` instruktioner för att fastställa sannolikheten för att mäta Quantum-tillstånd vid vissa angivna punkter i programmet.</span><span class="sxs-lookup"><span data-stu-id="9a256-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="9a256-197">Se även [testning och fel sökning](xref:microsoft.quantum.guide.testingdebugging) för mer information om- [`Assert`](xref:microsoft.quantum.intrinsic.assert) och- [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9a256-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="9a256-198">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9a256-198">Next steps</span></span>

<span data-ttu-id="9a256-199">Lär dig mer om [testning och fel sökning](xref:microsoft.quantum.guide.testingdebugging) i Q #.</span><span class="sxs-lookup"><span data-stu-id="9a256-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>