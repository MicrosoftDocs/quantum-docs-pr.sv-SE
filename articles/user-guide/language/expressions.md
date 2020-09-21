---
title: Uttryck i Q#
description: Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9bf28e3854eae1892692d7ca840e1860de2e2934
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835850"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="80e78-103">Uttryck i Q#</span><span class="sxs-lookup"><span data-stu-id="80e78-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="80e78-104">Numeriska uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-104">Numeric Expressions</span></span>

<span data-ttu-id="80e78-105">Numeriska uttryck är uttryck av typen `Int` , `BigInt` eller `Double` .</span><span class="sxs-lookup"><span data-stu-id="80e78-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="80e78-106">Det vill säga att de är antingen heltals-eller flytt ALS nummer.</span><span class="sxs-lookup"><span data-stu-id="80e78-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="80e78-107">`Int` litteraler i Q# skrivs som en sekvens med siffror.</span><span class="sxs-lookup"><span data-stu-id="80e78-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="80e78-108">Hexadecimala och binära heltal stöds och skrivs med `0x` `0b` prefixet respektive.</span><span class="sxs-lookup"><span data-stu-id="80e78-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="80e78-109">`BigInt` litteraler i Q# har ett efterföljande `l` eller `L` suffix.</span><span class="sxs-lookup"><span data-stu-id="80e78-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="80e78-110">Hexadecimala Big-heltal stöds och skrivs med ett "0x"-prefix.</span><span class="sxs-lookup"><span data-stu-id="80e78-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="80e78-111">Det innebär att följande är giltig användning av `BigInt` litteraler:</span><span class="sxs-lookup"><span data-stu-id="80e78-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="80e78-112">`Double` litteraler i Q# är flytt ALS siffror som skrivs med decimal siffror.</span><span class="sxs-lookup"><span data-stu-id="80e78-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="80e78-113">De kan skrivas med eller utan ett decimal tecken, `.` eller en exponentiell del som anges med "e" eller "e" (efter vilken endast ett möjligt negativt tecken och decimal siffror är giltiga).</span><span class="sxs-lookup"><span data-stu-id="80e78-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="80e78-114">Följande är giltiga `Double` litteraler: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="80e78-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="80e78-115">Med ett mat ris uttryck för valfri element typ kan du skapa ett `Int` uttryck med hjälp av den [`Length`](xref:microsoft.quantum.core.length) inbyggda funktionen, med mat ris uttrycket inom parentes.</span><span class="sxs-lookup"><span data-stu-id="80e78-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="80e78-116">Om till exempel `a` är kopplat till en matris, `Length(a)` är ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="80e78-117">Om `b` är en matris med heltals matriser, `Int[][]` `Length(b)` är antalet underordnade matriser i `b` och `Length(b[1])` är antalet heltal i den andra under matrisen i `b` .</span><span class="sxs-lookup"><span data-stu-id="80e78-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="80e78-118">Två numeriska uttryck av samma typ, de binära operatorerna `+` , `-` , `*` och `/` kan användas för att skapa ett nytt numeriskt uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="80e78-119">Typen för det nya uttrycket är samma som typerna av komponent uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="80e78-120">Med två heltals uttryck använder du den binära operatorn `^` (Power) för att skapa ett nytt heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="80e78-121">På samma sätt kan du också använda `^` med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="80e78-122">Slutligen kan du använda `^` med ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="80e78-123">I det här fallet måste den andra parametern passa in i 32 bitar. annars genererar den ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="80e78-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="80e78-124">Använd två heltals-eller Big-heltals uttryck för att skapa ett nytt heltals-eller Big-heltals uttryck med `%` operatorerna (Modulus), `&&&` (bitvis and), `|||` (bitvis or) eller `^^^` (Bitvis XOR).</span><span class="sxs-lookup"><span data-stu-id="80e78-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="80e78-125">Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till höger, använder du `<<<` operatorerna (aritmetisk vänster Shift) eller `>>>` (aritmetisk höger Shift) för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="80e78-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="80e78-126">Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.</span><span class="sxs-lookup"><span data-stu-id="80e78-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="80e78-127">Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; annars genererar den ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="80e78-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="80e78-128">Om det växlade talet är ett heltal tolkas Shift-beloppet, det vill säga `mod 64` en skift på 1 och en förskjutning på 65 har samma resultat.</span><span class="sxs-lookup"><span data-stu-id="80e78-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="80e78-129">För både heltals-och Big heltals värden är skiften aritmetiska.</span><span class="sxs-lookup"><span data-stu-id="80e78-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="80e78-130">Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="80e78-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="80e78-131">Det vill säga att flytta ett steg till vänster eller höger är detsamma som att multiplicera eller dividera med 2.</span><span class="sxs-lookup"><span data-stu-id="80e78-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="80e78-132">Heltals Division och heltals-Modulus följer samma beteende för negativa tal som C#.</span><span class="sxs-lookup"><span data-stu-id="80e78-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="80e78-133">Det vill säga `a % b` alltid samma tecken som `a` och `b * (a / b) + a % b` alltid lika med `a` .</span><span class="sxs-lookup"><span data-stu-id="80e78-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="80e78-134">Exempel:</span><span class="sxs-lookup"><span data-stu-id="80e78-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="80e78-135">5</span><span class="sxs-lookup"><span data-stu-id="80e78-135">5</span></span> | <span data-ttu-id="80e78-136">2</span><span class="sxs-lookup"><span data-stu-id="80e78-136">2</span></span> | <span data-ttu-id="80e78-137">2</span><span class="sxs-lookup"><span data-stu-id="80e78-137">2</span></span> | <span data-ttu-id="80e78-138">1</span><span class="sxs-lookup"><span data-stu-id="80e78-138">1</span></span> |
| <span data-ttu-id="80e78-139">5</span><span class="sxs-lookup"><span data-stu-id="80e78-139">5</span></span> | <span data-ttu-id="80e78-140">−2</span><span class="sxs-lookup"><span data-stu-id="80e78-140">-2</span></span> | <span data-ttu-id="80e78-141">−2</span><span class="sxs-lookup"><span data-stu-id="80e78-141">-2</span></span> | <span data-ttu-id="80e78-142">1</span><span class="sxs-lookup"><span data-stu-id="80e78-142">1</span></span> |
| <span data-ttu-id="80e78-143">-5</span><span class="sxs-lookup"><span data-stu-id="80e78-143">-5</span></span> | <span data-ttu-id="80e78-144">2</span><span class="sxs-lookup"><span data-stu-id="80e78-144">2</span></span> | <span data-ttu-id="80e78-145">−2</span><span class="sxs-lookup"><span data-stu-id="80e78-145">-2</span></span> | <span data-ttu-id="80e78-146">-1</span><span class="sxs-lookup"><span data-stu-id="80e78-146">-1</span></span> |
| <span data-ttu-id="80e78-147">-5</span><span class="sxs-lookup"><span data-stu-id="80e78-147">-5</span></span> | <span data-ttu-id="80e78-148">−2</span><span class="sxs-lookup"><span data-stu-id="80e78-148">-2</span></span> | <span data-ttu-id="80e78-149">2</span><span class="sxs-lookup"><span data-stu-id="80e78-149">2</span></span> | <span data-ttu-id="80e78-150">-1</span><span class="sxs-lookup"><span data-stu-id="80e78-150">-1</span></span> |

<span data-ttu-id="80e78-151">Big Integer-och Modulus-åtgärder fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="80e78-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="80e78-152">Med ett numeriskt uttryck kan du skapa ett nytt uttryck med hjälp av den `-` unära operatorn.</span><span class="sxs-lookup"><span data-stu-id="80e78-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="80e78-153">Det nya uttrycket är av samma typ som uttrycket för komponenten.</span><span class="sxs-lookup"><span data-stu-id="80e78-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="80e78-154">Med ett heltals-eller Big-heltals uttryck kan du skapa ett nytt uttryck av samma typ med den `~~~` unära operatorn (bitvis komplement).</span><span class="sxs-lookup"><span data-stu-id="80e78-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="80e78-155">Booleska uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-155">Boolean Expressions</span></span>

<span data-ttu-id="80e78-156">De två `Bool` literala värdena är `true` och `false` .</span><span class="sxs-lookup"><span data-stu-id="80e78-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="80e78-157">Om du har två uttryck av samma primitiva typ `==` kan de och `!=` binära operatorerna användas för att skapa ett `Bool` uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="80e78-158">Uttrycket är sant om de två uttrycken är lika och falskt om inte.</span><span class="sxs-lookup"><span data-stu-id="80e78-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="80e78-159">Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras.</span><span class="sxs-lookup"><span data-stu-id="80e78-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="80e78-160">Du kan till exempel använda operatorn "unwrap" `!` (förklaras i detalj vid [typer i Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)).</span><span class="sxs-lookup"><span data-stu-id="80e78-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="80e78-161">Likhets jämförelse för `Qubit` värden är identitets likhet, det vill säga om de två uttrycken identifierar samma qubit.</span><span class="sxs-lookup"><span data-stu-id="80e78-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="80e78-162">Tillstånden för de två qubits jämförs, används, mäts eller ändras inte i jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="80e78-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="80e78-163">Jämförelse av `Double` värden kan vara missvisande på grund av avrundnings effekter.</span><span class="sxs-lookup"><span data-stu-id="80e78-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="80e78-164">Till exempel `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="80e78-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="80e78-165">Två numeriska uttryck, de binära operatorerna,, `>` `<` `>=` och `<=` kan användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="80e78-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="80e78-166">Med valfria två booleska uttryck använder du den `and` binära operatorn för att skapa ett nytt booleskt uttryck som är sant om båda uttrycken är sanna.</span><span class="sxs-lookup"><span data-stu-id="80e78-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="80e78-167">På samma sätt `or` skapar med operatorn ett uttryck som är sant om något av de två uttrycken är sant.</span><span class="sxs-lookup"><span data-stu-id="80e78-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="80e78-168">Med alla booleska uttryck kan den `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.</span><span class="sxs-lookup"><span data-stu-id="80e78-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="80e78-169">Stränguttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-169">String expressions</span></span>

<span data-ttu-id="80e78-170">Q# tillåter att strängar används i `fail` instruktionen (förklaras i [kontroll flödet](xref:microsoft.quantum.guide.controlflow#fail-statement)) och i [`Message`](xref:microsoft.quantum.intrinsic.message) funktionen standard.</span><span class="sxs-lookup"><span data-stu-id="80e78-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="80e78-171">Det speciella beteendet för den senare beror på vilken simulator som används men skriver vanligt vis ett meddelande till värd konsolen när den anropas under ett Q# program.</span><span class="sxs-lookup"><span data-stu-id="80e78-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="80e78-172">Strängar i Q# är antingen litteraler eller interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="80e78-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="80e78-173">Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode-tecken som omges av dubbla citat tecken `" "` .</span><span class="sxs-lookup"><span data-stu-id="80e78-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="80e78-174">I en sträng använder du omvänt snedstreck `\` för att undvika ett dubbelt citat tecken ( `\"` ) eller infoga en ny rad ( `\n` ), en vagn retur ( `\r` ) eller en flik ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="80e78-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="80e78-175">Exempel:</span><span class="sxs-lookup"><span data-stu-id="80e78-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="80e78-176">Interpolerade strängar</span><span class="sxs-lookup"><span data-stu-id="80e78-176">Interpolated strings</span></span>

<span data-ttu-id="80e78-177">Q#Syntaxen för String-interpolation är en delmängd av C#-syntaxen.</span><span class="sxs-lookup"><span data-stu-id="80e78-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="80e78-178">Följande är viktiga punkter som de gäller för Q# :</span><span class="sxs-lookup"><span data-stu-id="80e78-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="80e78-179">För att identifiera en tecken sträng som en interpolerad sträng, lägga den med `$` symbolen.</span><span class="sxs-lookup"><span data-stu-id="80e78-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="80e78-180">Det får inte finnas något tomt utrymme mellan `$` och `"` som startar en tecken sträng.</span><span class="sxs-lookup"><span data-stu-id="80e78-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="80e78-181">Följande är ett grundläggande exempel [`Message`](xref:microsoft.quantum.intrinsic.message) som använder funktionen för att skriva resultatet av en mätning till-konsolen, tillsammans med andra Q# uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="80e78-182">Ett giltigt Q# uttryck kan visas i en interpolerad sträng.</span><span class="sxs-lookup"><span data-stu-id="80e78-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="80e78-183">Uttryck i en interpolerad sträng följer Q# syntax, inte C#-syntax.</span><span class="sxs-lookup"><span data-stu-id="80e78-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="80e78-184">Den viktigaste skillnaden är att Q# inte stöder orda Grant-interpolerade strängar (multi-line).</span><span class="sxs-lookup"><span data-stu-id="80e78-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="80e78-185">Mer information om C#-syntaxen finns i [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="80e78-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="80e78-186">Intervall uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-186">Range Expressions</span></span>

<span data-ttu-id="80e78-187">Med alla tre `Int` uttryck `start` , `step` och `stop` , `start .. step .. stop` är uttrycket ett intervall uttryck vars första element är, det `start` andra elementet är `start+step` , det tredje elementet är `start+step+step` och så vidare tills du skickar `stop` .</span><span class="sxs-lookup"><span data-stu-id="80e78-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="80e78-188">Ett intervall kan vara tomt om exempelvis `step` är positivt och `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="80e78-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="80e78-189">Intervallet är inkluderat i båda ändar.</span><span class="sxs-lookup"><span data-stu-id="80e78-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="80e78-190">Det vill säga om skillnaden mellan `start` och `stop` är ett heltals multipel av `step` , är det sista elementet i intervallet `stop` .</span><span class="sxs-lookup"><span data-stu-id="80e78-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="80e78-191">Med två `Int` uttryck `start` och `stop` uttrycket `start .. stop` är ett intervall uttryck som är lika med `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="80e78-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="80e78-192">Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start` . i så fall är intervallet tomt.</span><span class="sxs-lookup"><span data-stu-id="80e78-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="80e78-193">Några exempel intervall är:</span><span class="sxs-lookup"><span data-stu-id="80e78-193">Some example ranges are:</span></span>

- <span data-ttu-id="80e78-194">`1..3` är intervallet 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="80e78-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="80e78-195">`2..2..5` är intervallet 2, 4.</span><span class="sxs-lookup"><span data-stu-id="80e78-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="80e78-196">`2..2..6` är intervallet 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="80e78-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="80e78-197">`6..-2..2` är intervallet 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="80e78-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="80e78-198">`2..1` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="80e78-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="80e78-199">`2..6..7` är intervallet 2.</span><span class="sxs-lookup"><span data-stu-id="80e78-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="80e78-200">`2..2..1` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="80e78-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="80e78-201">`1..-1..2` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="80e78-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="80e78-202">Qubit-uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-202">Qubit Expressions</span></span>

<span data-ttu-id="80e78-203">De enda `Qubit` uttrycken är symboler som är kopplade till `Qubit` värden eller mat ris element `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="80e78-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="80e78-204">Det finns inga `Qubit` litteraler.</span><span class="sxs-lookup"><span data-stu-id="80e78-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="80e78-205">Pauli-uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-205">Pauli Expressions</span></span>

<span data-ttu-id="80e78-206">De fyra `Pauli` värdena, `PauliI` , `PauliX` , `PauliY` och `PauliZ` , är giltiga `Pauli` uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="80e78-207">Förutom så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="80e78-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="80e78-208">Resultat uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-208">Result Expressions</span></span>

<span data-ttu-id="80e78-209">De två `Result` värdena `One` och `Zero` , är giltiga `Result` uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="80e78-210">Förutom så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element `Result` .</span><span class="sxs-lookup"><span data-stu-id="80e78-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="80e78-211">Observera särskilt att `One` inte är detsamma som heltalet `1` och det finns ingen direkt konvertering mellan dem.</span><span class="sxs-lookup"><span data-stu-id="80e78-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="80e78-212">Samma sak gäller `Zero` och `0` .</span><span class="sxs-lookup"><span data-stu-id="80e78-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="80e78-213">Tuple-uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-213">Tuple Expressions</span></span>

<span data-ttu-id="80e78-214">En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, inom parentes.</span><span class="sxs-lookup"><span data-stu-id="80e78-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="80e78-215">Är till exempel `(1, One)` ett `(Int, Result)` uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="80e78-216">Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.</span><span class="sxs-lookup"><span data-stu-id="80e78-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="80e78-217">Användardefinierade typ uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="80e78-218">En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.</span><span class="sxs-lookup"><span data-stu-id="80e78-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="80e78-219">Om till exempel `IntPair` är en användardefinierad typ som baseras på `(Int, Int)` , `IntPair(2, 3)` är en giltig litteral av den typen.</span><span class="sxs-lookup"><span data-stu-id="80e78-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="80e78-220">Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.</span><span class="sxs-lookup"><span data-stu-id="80e78-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="80e78-221">Packa upp uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-221">Unwrap Expressions</span></span>

<span data-ttu-id="80e78-222">I Q# är unwrap-operatorn ett avslutande utrops tecken `!` .</span><span class="sxs-lookup"><span data-stu-id="80e78-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="80e78-223">Om är till exempel `IntPair` en användardefinierad typ med den underliggande typen `(Int, Int)` och `s` är en variabel med värde `IntPair(2, 3)` , `s!` är det `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="80e78-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="80e78-224">För användardefinierade typer som definieras i termer av andra användardefinierade typer, kan du upprepa operatorn unwrap.</span><span class="sxs-lookup"><span data-stu-id="80e78-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="80e78-225">Anger till exempel `s!!` dubblerat-värde för `s` .</span><span class="sxs-lookup"><span data-stu-id="80e78-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="80e78-226">Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair` och `t` är en variabel med värde `WrappedPair(IntPair(1,2))` , `t!!` är `(1,2)` det alltså.</span><span class="sxs-lookup"><span data-stu-id="80e78-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="80e78-227">`!`Operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.</span><span class="sxs-lookup"><span data-stu-id="80e78-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="80e78-228">`!` och `[]` BIND positions läge, som är, `a[i]![3]` läses som `((a[i])!)[3]` : ta det här `i` elementet i `a` , packa upp det och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).</span><span class="sxs-lookup"><span data-stu-id="80e78-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="80e78-229">Prioriteten hos `!` operatorn har en effekt som kanske inte är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="80e78-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="80e78-230">Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.</span><span class="sxs-lookup"><span data-stu-id="80e78-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="80e78-231">Exempel:</span><span class="sxs-lookup"><span data-stu-id="80e78-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="80e78-232">Mat ris uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-232">Array Expressions</span></span>

<span data-ttu-id="80e78-233">En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, inom hakparenteser `[]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="80e78-234">Alla element måste vara kompatibla med samma typ.</span><span class="sxs-lookup"><span data-stu-id="80e78-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="80e78-235">Med två matriser av samma typ använder du den binära `+` operatorn för att skapa en ny matris som är sammanfogningen av de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="80e78-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="80e78-236">Till exempel `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="80e78-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="80e78-237">Skapa matris</span><span class="sxs-lookup"><span data-stu-id="80e78-237">Array Creation</span></span>

<span data-ttu-id="80e78-238">Med en typ och ett `Int` uttryck använder du `new` operatorn för att allokera en ny matris med den aktuella storleken.</span><span class="sxs-lookup"><span data-stu-id="80e78-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="80e78-239">Allokera till exempel `new Int[i + 1]` en ny `Int` matris med `i + 1` element.</span><span class="sxs-lookup"><span data-stu-id="80e78-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="80e78-240">Tomma mat ris strängar, till exempel `[]` , är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="80e78-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="80e78-241">I stället kan du skapa en matris med längden noll genom att använda `new T[0]` , där `T` är en plats hållare för lämplig typ.</span><span class="sxs-lookup"><span data-stu-id="80e78-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="80e78-242">Elementen i en ny matris initieras till ett typ beroende standardvärde.</span><span class="sxs-lookup"><span data-stu-id="80e78-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="80e78-243">I de flesta fall är detta någon variation på noll.</span><span class="sxs-lookup"><span data-stu-id="80e78-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="80e78-244">Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.</span><span class="sxs-lookup"><span data-stu-id="80e78-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="80e78-245">Därför är standardvärdet en ogiltig referens som du inte kan använda utan att orsaka ett körnings fel som liknar en null-referens i språk som C# eller Java.</span><span class="sxs-lookup"><span data-stu-id="80e78-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="80e78-246">Matriser som innehåller qubits eller callables måste initieras med icke-standardvärden innan du kan använda elementen på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="80e78-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="80e78-247">För lämpliga initierings rutiner, se <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="80e78-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="80e78-248">Standardvärdena för varje typ är:</span><span class="sxs-lookup"><span data-stu-id="80e78-248">The default values for each type are:</span></span>

<span data-ttu-id="80e78-249">Typ</span><span class="sxs-lookup"><span data-stu-id="80e78-249">Type</span></span> | <span data-ttu-id="80e78-250">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="80e78-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="80e78-251">_Ogiltig qubit_</span><span class="sxs-lookup"><span data-stu-id="80e78-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="80e78-252">Det tomma intervallet, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="80e78-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="80e78-253">_Ogiltigt anrops bara_</span><span class="sxs-lookup"><span data-stu-id="80e78-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="80e78-254">Tuple-typer initierar element-för-element.</span><span class="sxs-lookup"><span data-stu-id="80e78-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="80e78-255">Mat ris element</span><span class="sxs-lookup"><span data-stu-id="80e78-255">Array Elements</span></span>

<span data-ttu-id="80e78-256">Använd ett mat ris uttryck och ett `Int` uttryck för att skapa ett nytt uttryck med hjälp av array element-operatorn `[]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="80e78-257">Det nya uttrycket är av samma typ som matrisens element typ.</span><span class="sxs-lookup"><span data-stu-id="80e78-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="80e78-258">Om till exempel `a` är kopplat till en matris av typen `Double` `a[4]` är det ett `Double` uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="80e78-259">Om mat ris uttrycket inte är en enkel identifierare måste du omge det med parenteser för att välja ett element.</span><span class="sxs-lookup"><span data-stu-id="80e78-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="80e78-260">Om till exempel `a` `b` båda är matriser av typen `Int` uttrycks ett element från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="80e78-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="80e78-261">Alla matriser i Q# är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="80e78-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="80e78-262">Det vill säga det första elementet i en matris `a` är alltid `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="80e78-263">Mat ris segment</span><span class="sxs-lookup"><span data-stu-id="80e78-263">Array Slices</span></span>

<span data-ttu-id="80e78-264">Med ett mat ris uttryck och ett `Range` uttryck bildar du ett nytt uttryck med hjälp av array-slice-operatorn `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="80e78-265">Det nya uttrycket är av samma typ som matrisen och innehåller de mat ris objekt som indexeras av elementen i `Range` , i den ordning som definieras av `Range` .</span><span class="sxs-lookup"><span data-stu-id="80e78-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="80e78-266">Om till exempel `a` är kopplat till en matris av typen `Double` , `a[3..-1..0]` är ett `Double[]` uttryck som innehåller de första fyra elementen i `a` men i omvänd ordning som de visas i `a` .</span><span class="sxs-lookup"><span data-stu-id="80e78-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="80e78-267">Om `Range` är tom, är den resulterande mat ris sektorn längden noll.</span><span class="sxs-lookup"><span data-stu-id="80e78-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="80e78-268">Precis som med referenser till mat ris element, om mat ris uttrycket inte är en enkel identifierare, måste du omge det med parenteser för att segmentera det.</span><span class="sxs-lookup"><span data-stu-id="80e78-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="80e78-269">Om till exempel `a` `b` båda är matriser av typen `Int` uttrycks en sektor från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="80e78-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="80e78-270">Uppskjutna start-/slut värden</span><span class="sxs-lookup"><span data-stu-id="80e78-270">Inferred start/end values</span></span>

<span data-ttu-id="80e78-271">Från och med vår [0,8-utgåva](xref:microsoft.quantum.relnotes)stöder vi sammanhangsbaserade uttryck för intervall segmentering.</span><span class="sxs-lookup"><span data-stu-id="80e78-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="80e78-272">I synnerhet kan du utelämna intervallens start-och slut värden i kontexten för ett intervall segment uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="80e78-273">I så fall tillämpar kompilatorn följande regler för att härleda de avsedda avgränsarna för intervallet:</span><span class="sxs-lookup"><span data-stu-id="80e78-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="80e78-274">Om *Start* värde för intervall utelämnas anges värdet för uppskjutet start värde</span><span class="sxs-lookup"><span data-stu-id="80e78-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="80e78-275">är noll om inget steg har angetts eller det angivna steget är positivt.</span><span class="sxs-lookup"><span data-stu-id="80e78-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="80e78-276">är längden på den segmenterade matrisen minus en om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="80e78-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="80e78-277">Om slutvärdet *för intervallet utelämnas visas värdet för* det härledda slut värdet</span><span class="sxs-lookup"><span data-stu-id="80e78-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="80e78-278">är längden på den segmenterade matrisen minus en om inget steg har angetts eller om det angivna steget är positivt.</span><span class="sxs-lookup"><span data-stu-id="80e78-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="80e78-279">är noll om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="80e78-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="80e78-280">Några exempel är:</span><span class="sxs-lookup"><span data-stu-id="80e78-280">Some examples are:</span></span>

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a><span data-ttu-id="80e78-281">Kopiera och uppdatera uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="80e78-282">Eftersom alla Q# typer är värde typer (med qubits som tar en lite speciell roll) skapas en "kopia" av en "kopia" när ett värde är kopplat till en symbol eller när en symbol har bundits.</span><span class="sxs-lookup"><span data-stu-id="80e78-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="80e78-283">Detta är att säga att beteendet i Q# är detsamma som om en kopia skapades med en tilldelnings operator.</span><span class="sxs-lookup"><span data-stu-id="80e78-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="80e78-284">I praktiken återskapas bara relevanta delar vid behov.</span><span class="sxs-lookup"><span data-stu-id="80e78-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="80e78-285">Detta påverkar hur du kopierar matriser eftersom det inte går att uppdatera mat ris objekt.</span><span class="sxs-lookup"><span data-stu-id="80e78-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="80e78-286">Om du vill ändra en befintlig matris måste du använda en *kopierings-och-uppdaterings* funktion.</span><span class="sxs-lookup"><span data-stu-id="80e78-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="80e78-287">Du kan skapa en ny matris från en befintlig matris via ett *kopierings-och-uppdatera* -uttryck som använder operatorerna `w/` och `<-` .</span><span class="sxs-lookup"><span data-stu-id="80e78-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="80e78-288">Ett kopierings-och-uppdatering-uttryck är ett uttryck i formuläret `expression1 w/ expression2 <- expression3` där</span><span class="sxs-lookup"><span data-stu-id="80e78-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="80e78-289">`expression1` måste vara `T[]` av typen `T` .</span><span class="sxs-lookup"><span data-stu-id="80e78-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="80e78-290">`expression2` definierar vilka index i matrisen som anges i `expression1` att ändra.</span><span class="sxs-lookup"><span data-stu-id="80e78-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="80e78-291">`expression2` måste vara antingen typ `Int` eller typ `Range` .</span><span class="sxs-lookup"><span data-stu-id="80e78-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="80e78-292">`expression3` är de värden som används för att uppdatera element i `expression1` , baserat på de index som anges i `expression2` .</span><span class="sxs-lookup"><span data-stu-id="80e78-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="80e78-293">Om `expression2` är Type `Int` `expression3` måste vara av typen `T` .</span><span class="sxs-lookup"><span data-stu-id="80e78-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="80e78-294">Om `expression2` är Type `Range` `expression3` måste vara av typen `T[]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="80e78-295">Exempel: Copy-och-Update-uttrycket `arr w/ idx <- value` skapar en ny matris med alla element som har angetts till motsvarande element i `arr` , förutom de element som anges av `idx` , vilket är inställt på värdet (erna) i `value` .</span><span class="sxs-lookup"><span data-stu-id="80e78-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="80e78-296">Anges `arr` innehåller matrisen `[0,1,2,3]` och sedan</span><span class="sxs-lookup"><span data-stu-id="80e78-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="80e78-297">`arr w/ 0 <- 10` är matrisen `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="80e78-298">`arr w/ 2 <- 10` är matrisen `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="80e78-299">`arr w/ 0..2..3 <- [10,12]` är matrisen `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="80e78-300">Kopiera och uppdatera uttryck för namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="80e78-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="80e78-301">Det finns liknande uttryck för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="80e78-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="80e78-302">Anta till exempel typen</span><span class="sxs-lookup"><span data-stu-id="80e78-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="80e78-303">Om `c` innehåller värdet av typen `Complex(1., -1.)` `c w/ Re <- 0.` är det ett uttryck av typen `Complex` som utvärderas till `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="80e78-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="80e78-304">Ojämna matriser</span><span class="sxs-lookup"><span data-stu-id="80e78-304">Jagged Arrays</span></span>

<span data-ttu-id="80e78-305">En taggad matris, som ibland kallas matriser, är en matris vars element är matriser.</span><span class="sxs-lookup"><span data-stu-id="80e78-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="80e78-306">Elementen i en taggad matris kan ha olika storlekar.</span><span class="sxs-lookup"><span data-stu-id="80e78-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="80e78-307">I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.</span><span class="sxs-lookup"><span data-stu-id="80e78-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a><span data-ttu-id="80e78-308">Matriser med callables</span><span class="sxs-lookup"><span data-stu-id="80e78-308">Arrays of callables</span></span> 

<span data-ttu-id="80e78-309">Du kan också skapa en matris med callables.</span><span class="sxs-lookup"><span data-stu-id="80e78-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="80e78-310">Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.</span><span class="sxs-lookup"><span data-stu-id="80e78-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="80e78-311">Element typen för matrisen stöder alla [functors](xref:microsoft.quantum.guide.operationsfunctions) som stöds av alla element.</span><span class="sxs-lookup"><span data-stu-id="80e78-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="80e78-312">Till exempel, `Op1` `Op2` , och `Op3` alla är `Qubit[] => Unit` åtgärder, men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="80e78-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="80e78-313">`[Op1, Op2]` är en matris med `(Qubit[] => Unit)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80e78-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="80e78-314">`[Op1, Op3]` är en matris med `(Qubit[] => Unit is Adj)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80e78-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="80e78-315">`[Op2, Op3]` är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80e78-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="80e78-316">Men även om åtgärderna `(Qubit[] => Unit is Adj)` och `(Qubit[] => Unit is Ctl)` har den gemensamma bastypen för `(Qubit[] => Unit)` , delar dessa *arrays* åtgärder inte med någon gemensam bastyp.</span><span class="sxs-lookup"><span data-stu-id="80e78-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="80e78-317">Skulle till exempel `[[Op1], [Op2]]` kunna generera ett fel eftersom det försöker skapa en matris med de två inkompatibla mat ris typerna `(Qubit[] => Unit is Adj)[]` och `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="80e78-318">Mer information om callables finns i [anrops bara uttryck](#callable-expressions) på den här sidan eller [åtgärder och funktioner Q# i ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="80e78-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="80e78-319">Villkors uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-319">Conditional Expressions</span></span>

<span data-ttu-id="80e78-320">Om du har två uttryck av samma typ och ett booleskt uttryck bildar du ett villkors uttryck med hjälp av frågetecknet, `?` och det lodräta fältet `|` .</span><span class="sxs-lookup"><span data-stu-id="80e78-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="80e78-321">Anges `a==b ? c | d` värdet för villkors uttrycket `c` om `a==b` är sant och `d` om det är falskt.</span><span class="sxs-lookup"><span data-stu-id="80e78-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="80e78-322">Villkors uttryck med callables</span><span class="sxs-lookup"><span data-stu-id="80e78-322">Conditional expressions with callables</span></span>

<span data-ttu-id="80e78-323">Villkors uttryck kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.</span><span class="sxs-lookup"><span data-stu-id="80e78-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="80e78-324">I det här fallet är typen av villkors uttryck en åtgärd med indata och utdata som stöder alla functors som stöds av båda uttrycken.</span><span class="sxs-lookup"><span data-stu-id="80e78-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="80e78-325">Till exempel, `Op1` `Op2` , och `Op3` alla `Qubit[]=>Unit` , men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="80e78-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="80e78-326">`flag ? Op1 | Op2` är en `(Qubit[] => Unit)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="80e78-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="80e78-327">`flag ? Op1 | Op3` är en `(Qubit[] => Unit is Adj)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="80e78-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="80e78-328">`flag ? Op2 | Op3` är en `(Qubit[] => Unit is Ctl)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="80e78-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="80e78-329">Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop, sker bara anropet om det är det som är värdet för anropet.</span><span class="sxs-lookup"><span data-stu-id="80e78-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="80e78-330">Om t. ex. `a==b ? C(qs) | D(qs)` `a==b` är sant, så `C` anropas åtgärden och om den är false `D` anropas bara åtgärden.</span><span class="sxs-lookup"><span data-stu-id="80e78-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="80e78-331">Den här metoden liknar *korta kretsar* på andra språk.</span><span class="sxs-lookup"><span data-stu-id="80e78-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="80e78-332">Anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-332">Callable Expressions</span></span>

<span data-ttu-id="80e78-333">En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.</span><span class="sxs-lookup"><span data-stu-id="80e78-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="80e78-334">Är till exempel `X` en åtgärds-literal som refererar till standard biblioteks `X` åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.</span><span class="sxs-lookup"><span data-stu-id="80e78-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="80e78-335">Om en åtgärd har stöd för `Adjoint` Functor `Adjoint op` är ett åtgärds uttryck.</span><span class="sxs-lookup"><span data-stu-id="80e78-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="80e78-336">På samma sätt `Controlled` `Controlled op` är det ett åtgärds uttryck om åtgärden stöder Functor.</span><span class="sxs-lookup"><span data-stu-id="80e78-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="80e78-337">Mer information om typerna av dessa uttryck finns i avsnittet om hur du [anropar en specialisering](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="80e78-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="80e78-338">Functors ( `Adjoint` och `Controlled` ) binder mer nära varandra än alla andra operatorer, förutom unwrap-operatorn `!` och mat ris indexering med `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="80e78-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="80e78-339">Därför är följande giltiga, förutsatt att de åtgärder som har stöd för de functors som används:</span><span class="sxs-lookup"><span data-stu-id="80e78-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="80e78-340">Typ-parametriserade anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="80e78-341">Du kan använda en anropad literal som ett värde, till exempel för att tilldela den till en variabel eller skicka den till ett annat anrop.</span><span class="sxs-lookup"><span data-stu-id="80e78-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="80e78-342">I det här fallet, om anropet har [typ parametrar](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), måste du ange parametrarna som en del av det anropade värdet.</span><span class="sxs-lookup"><span data-stu-id="80e78-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="80e78-343">Ett anrops bara värde kan inte ha ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="80e78-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="80e78-344">Om är till exempel `Fun` en funktion med signaturen `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="80e78-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="80e78-345">Anrops anrops anrops uttryck</span><span class="sxs-lookup"><span data-stu-id="80e78-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="80e78-346">Ett anrops bara uttryck (funktion eller funktion) och ett tuple-uttryck av indatatypen för den anropande signaturen, kan du skapa ett anrops *uttryck* genom att lägga till tuple-uttrycket i det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="80e78-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="80e78-347">Typen av anrops uttryck är utdatatypen för den anropande signaturen.</span><span class="sxs-lookup"><span data-stu-id="80e78-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="80e78-348">Om är till exempel en `Op` åtgärd med signaturen `((Int, Qubit) => Double)` , `Op(3, qubit1)` är ett uttryck av typen `Double` .</span><span class="sxs-lookup"><span data-stu-id="80e78-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="80e78-349">På samma sätt `Sin` `(Double -> Double)` är ett `Sin(0.1)` uttryck av typen om är en funktion med signaturen `Double` .</span><span class="sxs-lookup"><span data-stu-id="80e78-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="80e78-350">Slutligen, om `Builder` är en funktion med signaturen `(Int -> (Int -> Int))` , `Builder(3)` är en funktion från `Int` till `Int` .</span><span class="sxs-lookup"><span data-stu-id="80e78-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="80e78-351">Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="80e78-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="80e78-352">För att anropa resultatet av anrop `Builder` från föregående stycke är därför rätt syntax:</span><span class="sxs-lookup"><span data-stu-id="80e78-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="80e78-353">När du anropar en [typ-parameter](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) som kan anropas kan du ange de faktiska typ parametrarna inom vinkelparenteser `< >` efter det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="80e78-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="80e78-354">Den här åtgärden är vanligt vis onödigt eftersom Q# kompilatorn härleder de faktiska typerna.</span><span class="sxs-lookup"><span data-stu-id="80e78-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="80e78-355">*Det krävs* dock för [partiella program](xref:microsoft.quantum.guide.operationsfunctions#partial-application) om ett argument av typen parameter lämnas ospecificerade.</span><span class="sxs-lookup"><span data-stu-id="80e78-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="80e78-356">Det är också användbart när du skickar åtgärder med olika Functor-funktioner som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="80e78-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="80e78-357">Om du till exempel `Func` har signatur och har signatur, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` och `Op3` har signatur `(Qubit[] => Unit)` , för att anropa `Func` med `Op1` som första argument, `Op2` som den andra, och `Op3` som tredje:</span><span class="sxs-lookup"><span data-stu-id="80e78-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="80e78-358">Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.</span><span class="sxs-lookup"><span data-stu-id="80e78-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="80e78-359">Prioritet för Operator</span><span class="sxs-lookup"><span data-stu-id="80e78-359">Operator Precedence</span></span>

* <span data-ttu-id="80e78-360">Alla binära operatorer är rätt associerade, förutom för `^` .</span><span class="sxs-lookup"><span data-stu-id="80e78-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="80e78-361">Hakparenteser, `[ ]` , för mat ris segmentering och indexering, bind före valfri operator.</span><span class="sxs-lookup"><span data-stu-id="80e78-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="80e78-362">Functors `Adjoint` och `Controlled` BIND efter mat ris indexering, men före alla andra operatorer.</span><span class="sxs-lookup"><span data-stu-id="80e78-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="80e78-363">Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.</span><span class="sxs-lookup"><span data-stu-id="80e78-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="80e78-364">Q# operatorer i prioritetsordning, från högsta till lägsta:</span><span class="sxs-lookup"><span data-stu-id="80e78-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="80e78-365">Operator</span><span class="sxs-lookup"><span data-stu-id="80e78-365">Operator</span></span> | <span data-ttu-id="80e78-366">Ariteten</span><span class="sxs-lookup"><span data-stu-id="80e78-366">Arity</span></span> | <span data-ttu-id="80e78-367">Description</span><span class="sxs-lookup"><span data-stu-id="80e78-367">Description</span></span> | <span data-ttu-id="80e78-368">Operands typer</span><span class="sxs-lookup"><span data-stu-id="80e78-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="80e78-369">avslutande `!`</span><span class="sxs-lookup"><span data-stu-id="80e78-369">trailing `!`</span></span> | <span data-ttu-id="80e78-370">Unär</span><span class="sxs-lookup"><span data-stu-id="80e78-370">Unary</span></span> | <span data-ttu-id="80e78-371">Packa upp</span><span class="sxs-lookup"><span data-stu-id="80e78-371">Unwrap</span></span> | <span data-ttu-id="80e78-372">Valfri användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="80e78-372">Any user-defined type</span></span>
 <span data-ttu-id="80e78-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="80e78-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="80e78-374">Unär</span><span class="sxs-lookup"><span data-stu-id="80e78-374">Unary</span></span> | <span data-ttu-id="80e78-375">Numeriskt negativ, bitvis komplement, logisk negation</span><span class="sxs-lookup"><span data-stu-id="80e78-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="80e78-376">`Int`, `BigInt` eller `Double` för `-` , `Int` eller `BigInt` `~~~` för `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="80e78-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="80e78-377">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-377">Binary</span></span> | <span data-ttu-id="80e78-378">Heltals effekt</span><span class="sxs-lookup"><span data-stu-id="80e78-378">Integer power</span></span> | <span data-ttu-id="80e78-379">`Int` eller `BigInt` för basen `Int` för exponenten</span><span class="sxs-lookup"><span data-stu-id="80e78-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="80e78-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="80e78-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="80e78-381">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-381">Binary</span></span> | <span data-ttu-id="80e78-382">Division, multiplikation, heltals-modulus</span><span class="sxs-lookup"><span data-stu-id="80e78-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="80e78-383">`Int`, `BigInt` eller `Double` för `/` och `*` , `Int` eller `BigInt` för `%`</span><span class="sxs-lookup"><span data-stu-id="80e78-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="80e78-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="80e78-384">`+`, `-`</span></span> | <span data-ttu-id="80e78-385">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-385">Binary</span></span> | <span data-ttu-id="80e78-386">Kombination av addition eller sträng och matris, subtraktion</span><span class="sxs-lookup"><span data-stu-id="80e78-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="80e78-387">`Int``BigInt`eller `Double` , även `String` eller valfri mat ris typ för`+`</span><span class="sxs-lookup"><span data-stu-id="80e78-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="80e78-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="80e78-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="80e78-389">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-389">Binary</span></span> | <span data-ttu-id="80e78-390">Vänster SKIFT, höger Skift</span><span class="sxs-lookup"><span data-stu-id="80e78-390">Left shift, right shift</span></span> | <span data-ttu-id="80e78-391">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="80e78-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="80e78-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="80e78-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="80e78-393">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-393">Binary</span></span> | <span data-ttu-id="80e78-394">Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="80e78-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="80e78-395">`Int``BigInt`eller`Double`</span><span class="sxs-lookup"><span data-stu-id="80e78-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="80e78-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="80e78-396">`==`, `!=`</span></span> | <span data-ttu-id="80e78-397">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-397">Binary</span></span> | <span data-ttu-id="80e78-398">lika med, inte lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="80e78-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="80e78-399">vilken primitiv typ som helst</span><span class="sxs-lookup"><span data-stu-id="80e78-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="80e78-400">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-400">Binary</span></span> | <span data-ttu-id="80e78-401">Bitvis och</span><span class="sxs-lookup"><span data-stu-id="80e78-401">Bitwise AND</span></span> | <span data-ttu-id="80e78-402">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="80e78-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="80e78-403">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-403">Binary</span></span> | <span data-ttu-id="80e78-404">Bitvis XOR</span><span class="sxs-lookup"><span data-stu-id="80e78-404">Bitwise XOR</span></span> | <span data-ttu-id="80e78-405">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="80e78-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="80e78-406">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-406">Binary</span></span> | <span data-ttu-id="80e78-407">Bitvis eller</span><span class="sxs-lookup"><span data-stu-id="80e78-407">Bitwise OR</span></span> | <span data-ttu-id="80e78-408">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="80e78-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="80e78-409">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-409">Binary</span></span> | <span data-ttu-id="80e78-410">Logiskt AND</span><span class="sxs-lookup"><span data-stu-id="80e78-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="80e78-411">Binär</span><span class="sxs-lookup"><span data-stu-id="80e78-411">Binary</span></span> | <span data-ttu-id="80e78-412">Logiskt OR</span><span class="sxs-lookup"><span data-stu-id="80e78-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="80e78-413">Binär/ternär</span><span class="sxs-lookup"><span data-stu-id="80e78-413">Binary/Ternary</span></span> | <span data-ttu-id="80e78-414">Intervall operator</span><span class="sxs-lookup"><span data-stu-id="80e78-414">Range operator</span></span> | `Int`
 <span data-ttu-id="80e78-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="80e78-415">`?` `|`</span></span> | <span data-ttu-id="80e78-416">Ternär</span><span class="sxs-lookup"><span data-stu-id="80e78-416">Ternary</span></span> | <span data-ttu-id="80e78-417">Villkorsstyrd</span><span class="sxs-lookup"><span data-stu-id="80e78-417">Conditional</span></span> | <span data-ttu-id="80e78-418">`Bool` för den vänstra sidan</span><span class="sxs-lookup"><span data-stu-id="80e78-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="80e78-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="80e78-419">`w/` `<-`</span></span> | <span data-ttu-id="80e78-420">Ternär</span><span class="sxs-lookup"><span data-stu-id="80e78-420">Ternary</span></span> | <span data-ttu-id="80e78-421">Kopiera och uppdatera</span><span class="sxs-lookup"><span data-stu-id="80e78-421">Copy-and-update</span></span> | <span data-ttu-id="80e78-422">Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="80e78-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="80e78-423">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="80e78-423">Next steps</span></span>

<span data-ttu-id="80e78-424">Nu när du kan arbeta med uttryck i Q# , kan du gå vidare till [åtgärder och Q# funktioner i](xref:microsoft.quantum.guide.operationsfunctions) för att lära dig hur du definierar och anropar-åtgärder och-funktioner.</span><span class="sxs-lookup"><span data-stu-id="80e78-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
