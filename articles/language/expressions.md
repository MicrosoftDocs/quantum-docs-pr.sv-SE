---
title: 'Q # uttryck'
description: 'Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907417"
---
# <a name="expressions"></a><span data-ttu-id="8dffe-103">Uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="8dffe-104">Baserat</span><span class="sxs-lookup"><span data-stu-id="8dffe-104">Grouping</span></span>

<span data-ttu-id="8dffe-105">Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="8dffe-106">`(7)` är till exempel ett `Int` uttryck, `([1,2,3])` är ett uttryck av typen matris med `Int`s och `((1,2))` är ett uttryck med typ `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="8dffe-107">Motsvarigheten mellan enkla värden och tupler med ett enda element som beskrivs i [typ modellen](xref:microsoft.quantum.language.type-model#tuple-types) tar bort tvetydigheten mellan `(6)` som en grupp och `(6)` som en tupel med ett enda element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="8dffe-108">Symboler</span><span class="sxs-lookup"><span data-stu-id="8dffe-108">Symbols</span></span>

<span data-ttu-id="8dffe-109">Namnet på en symbol som är kopplad till eller tilldelats ett värde av typen `'T` är ett uttryck av typen `'T`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="8dffe-110">Om till exempel symbolen `count` är kopplad till heltal svärdet `5`, är `count` ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="8dffe-111">Numeriska uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-111">Numeric Expressions</span></span>

<span data-ttu-id="8dffe-112">Numeriska uttryck är uttryck av typen `Int`, `BigInt`eller `Double`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="8dffe-113">Det vill säga att de är antingen heltals-eller flytt ALS nummer.</span><span class="sxs-lookup"><span data-stu-id="8dffe-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="8dffe-114">`Int` litteraler i Q # är identiska med heltals strängar i C#, förutom att ingen efterföljande "l" eller "l" krävs (eller tillåts).</span><span class="sxs-lookup"><span data-stu-id="8dffe-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="8dffe-115">Hexadecimala och binära heltal stöds med prefixet "0x" och "0b".</span><span class="sxs-lookup"><span data-stu-id="8dffe-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="8dffe-116">`BigInt` litteraler i Q # är identiska med Big heltals strängar i .NET, med ett efterföljande "l" eller "L".</span><span class="sxs-lookup"><span data-stu-id="8dffe-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="8dffe-117">Hexadecimala Big heltal stöds med ett "0x"-prefix.</span><span class="sxs-lookup"><span data-stu-id="8dffe-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="8dffe-118">Därför är följande giltiga användnings områden för `BigInt` litteraler:</span><span class="sxs-lookup"><span data-stu-id="8dffe-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="8dffe-119">`Double` litteraler i Q # är identiska med dubbla strängar i C#, förutom att ingen efterföljande "d" eller "d" krävs (eller tillåts).</span><span class="sxs-lookup"><span data-stu-id="8dffe-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="8dffe-120">Med ett mat ris uttryck för valfri element typ kan ett `Int` uttryck skapas med hjälp av den inbyggda funktionen `Length`, med mat ris uttrycket omsluts av parenteser, `(` och `)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="8dffe-121">Om `a` till exempel är kopplat till en matris, är `Length(a)` ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="8dffe-122">Om `b` är en matris med heltals matriser `Int[][]``Length(b)` är antalet underordnade matriser i `b`och `Length(b[1])` är antalet heltal i den andra under matrisen i `b`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="8dffe-123">Med två numeriska uttryck av samma typ kan de binära operatorerna `+`, `-`, `*`och `/` användas för att skapa ett nytt numeriskt uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="8dffe-124">Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="8dffe-125">Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="8dffe-126">På samma sätt kan `^` användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="8dffe-127">Slutligen kan `^` användas med ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="8dffe-128">I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="8dffe-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="8dffe-129">Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big-heltals uttryck skapas med operatorerna `%` (Modulus), `&&&` (bitvis AND), `|||` (bitvis OR) eller `^^^` (Bitvis XOR).</span><span class="sxs-lookup"><span data-stu-id="8dffe-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="8dffe-130">Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till höger, kan `<<<` (aritmetiska vänstra Shift) eller `>>>` (aritmetiska höger Shift) operatörer användas för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="8dffe-131">Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.</span><span class="sxs-lookup"><span data-stu-id="8dffe-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="8dffe-132">Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="8dffe-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="8dffe-133">Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet `mod 64`; det vill säga en skift på 1 och en förskjutning på 65 har samma resultat.</span><span class="sxs-lookup"><span data-stu-id="8dffe-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="8dffe-134">För både heltals-och Big heltals värden är skiften aritmetiska.</span><span class="sxs-lookup"><span data-stu-id="8dffe-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="8dffe-135">Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="8dffe-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="8dffe-136">Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.</span><span class="sxs-lookup"><span data-stu-id="8dffe-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="8dffe-137">Heltals Division och heltals-Modulus följer samma beteende för negativa C#tal som.</span><span class="sxs-lookup"><span data-stu-id="8dffe-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="8dffe-138">Det vill `a % b` alltid ha samma tecken som `a`och `b * (a / b) + a % b` är alltid lika med `a`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="8dffe-139">Några exempel:</span><span class="sxs-lookup"><span data-stu-id="8dffe-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="8dffe-140">5</span><span class="sxs-lookup"><span data-stu-id="8dffe-140">5</span></span> | <span data-ttu-id="8dffe-141">2</span><span class="sxs-lookup"><span data-stu-id="8dffe-141">2</span></span> | <span data-ttu-id="8dffe-142">2</span><span class="sxs-lookup"><span data-stu-id="8dffe-142">2</span></span> | <span data-ttu-id="8dffe-143">1</span><span class="sxs-lookup"><span data-stu-id="8dffe-143">1</span></span>
 <span data-ttu-id="8dffe-144">5</span><span class="sxs-lookup"><span data-stu-id="8dffe-144">5</span></span> | <span data-ttu-id="8dffe-145">-2</span><span class="sxs-lookup"><span data-stu-id="8dffe-145">-2</span></span> | <span data-ttu-id="8dffe-146">-2</span><span class="sxs-lookup"><span data-stu-id="8dffe-146">-2</span></span> | <span data-ttu-id="8dffe-147">1</span><span class="sxs-lookup"><span data-stu-id="8dffe-147">1</span></span>
 <span data-ttu-id="8dffe-148">-5</span><span class="sxs-lookup"><span data-stu-id="8dffe-148">-5</span></span> | <span data-ttu-id="8dffe-149">2</span><span class="sxs-lookup"><span data-stu-id="8dffe-149">2</span></span> | <span data-ttu-id="8dffe-150">-2</span><span class="sxs-lookup"><span data-stu-id="8dffe-150">-2</span></span> | <span data-ttu-id="8dffe-151">-1</span><span class="sxs-lookup"><span data-stu-id="8dffe-151">-1</span></span>
 <span data-ttu-id="8dffe-152">-5</span><span class="sxs-lookup"><span data-stu-id="8dffe-152">-5</span></span> | <span data-ttu-id="8dffe-153">-2</span><span class="sxs-lookup"><span data-stu-id="8dffe-153">-2</span></span> | <span data-ttu-id="8dffe-154">2</span><span class="sxs-lookup"><span data-stu-id="8dffe-154">2</span></span> | <span data-ttu-id="8dffe-155">-1</span><span class="sxs-lookup"><span data-stu-id="8dffe-155">-1</span></span>

<span data-ttu-id="8dffe-156">Big Integer-Division och Modulus fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="8dffe-157">Med ett numeriskt uttryck kan ett nytt uttryck skapas med hjälp av `-` unära operatorn.</span><span class="sxs-lookup"><span data-stu-id="8dffe-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="8dffe-158">Det nya uttrycket är av samma typ som komponent uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="8dffe-159">Med ett heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med den unära operatorn `~~~` (bitvis komplement).</span><span class="sxs-lookup"><span data-stu-id="8dffe-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="8dffe-160">Booleska uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-160">Boolean Expressions</span></span>

<span data-ttu-id="8dffe-161">De två `Bool` literala värdena är `true` och `false`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="8dffe-162">Med två uttryck av samma primitiva typ kan `==` och `!=` binära operatorer användas för att skapa ett `Bool`-uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="8dffe-163">Uttrycket är sant om de två uttrycken är lika och falskt om inte.</span><span class="sxs-lookup"><span data-stu-id="8dffe-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="8dffe-164">Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras.</span><span class="sxs-lookup"><span data-stu-id="8dffe-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="8dffe-165">Till exempel använder operatorn "unwrap" `!` (förklaras på [sidan för Q # typ modell](xref:microsoft.quantum.language.type-model#user-defined-types)).</span><span class="sxs-lookup"><span data-stu-id="8dffe-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="8dffe-166">Likhets jämförelse för `Qubit` värden är identitets likhet; det vill säga om de två uttrycken identifierar samma qubit.</span><span class="sxs-lookup"><span data-stu-id="8dffe-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="8dffe-167">Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="8dffe-168">Likhets jämförelse för `Double` värden kan vara missvisande på grund av avrundnings effekter.</span><span class="sxs-lookup"><span data-stu-id="8dffe-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="8dffe-169">`49.0 * (1.0/49.0) != 1.0`till exempel.</span><span class="sxs-lookup"><span data-stu-id="8dffe-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="8dffe-170">Med två numeriska uttryck kan de binära operatorerna `>`, `<`, `>=`och `<=` användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="8dffe-171">Med de två booleska uttrycken kan `and` och `or` binära operatorer användas för att skapa ett nytt booleskt uttryck som är sant om båda av (ansvars båda eller båda) de två uttrycken är sanna.</span><span class="sxs-lookup"><span data-stu-id="8dffe-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="8dffe-172">Med alla booleska uttryck kan `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="8dffe-173">Sträng uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-173">String Expressions</span></span>

<span data-ttu-id="8dffe-174">Q # tillåter att strängar används i `fail`-instruktionen och `Log` standard-funktionen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="8dffe-175">Strängar i Q # är antingen litteraler eller interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="8dffe-176">Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode-tecken som omges av dubbla citat tecken `"`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="8dffe-177">I en sträng kan du använda det omvända snedstrecket `\` för att undvika ett dubbelt citat tecken och infoga en ny rad som `\n`, en vagn retur som `\r`och en flik som `\t`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="8dffe-178">Exempel:</span><span class="sxs-lookup"><span data-stu-id="8dffe-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="8dffe-179">Q #-syntaxen för String-interpolation är en delmängd av C# 7,0-syntaxen. Q # stöder inte orda Grant (multi-line) interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="8dffe-180">Se [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) för C# syntaxen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="8dffe-181">Uttryck i en interpolerad sträng följer Q # syntax, inte C# syntax.</span><span class="sxs-lookup"><span data-stu-id="8dffe-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="8dffe-182">Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.</span><span class="sxs-lookup"><span data-stu-id="8dffe-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="8dffe-183">Qubit-uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-183">Qubit Expressions</span></span>

<span data-ttu-id="8dffe-184">De enda `Qubit` uttrycken är symboler som är kopplade till `Qubit` värden eller mat ris element i `Qubit` matriser.</span><span class="sxs-lookup"><span data-stu-id="8dffe-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="8dffe-185">Det finns inga `Qubit` litteraler.</span><span class="sxs-lookup"><span data-stu-id="8dffe-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="8dffe-186">Pauli-uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-186">Pauli Expressions</span></span>

<span data-ttu-id="8dffe-187">De fyra `Pauli` värdena, `PauliI`, `PauliX`, `PauliY`och `PauliZ`är alla giltiga `Pauli` uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="8dffe-188">Andra än så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element i `Pauli` matriser.</span><span class="sxs-lookup"><span data-stu-id="8dffe-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="8dffe-189">Resultat uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-189">Result Expressions</span></span>

<span data-ttu-id="8dffe-190">De två `Result` värdena `One` och `Zero`är giltiga `Result` uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="8dffe-191">Andra än så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element i `Result` matriser.</span><span class="sxs-lookup"><span data-stu-id="8dffe-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="8dffe-192">Observera särskilt att `One` inte är samma som det heltal som `1`, och det inte finns någon direkt konvertering mellan dem.</span><span class="sxs-lookup"><span data-stu-id="8dffe-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="8dffe-193">Detsamma gäller för `Zero` och `0`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="8dffe-194">Intervall uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-194">Range Expressions</span></span>

<span data-ttu-id="8dffe-195">Med de tre `Int` uttrycken `start`, `step`och `stop`, är `start .. step .. stop` ett intervall uttryck vars första element är `start`, det andra elementet är `start+step`, det tredje elementet är `start+step+step`osv., tills `stop` skickas.</span><span class="sxs-lookup"><span data-stu-id="8dffe-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="8dffe-196">Ett intervall kan vara tomt om till exempel `step` är positivt och `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="8dffe-197">Det sista elementet i intervallet är `stop` om skillnaden mellan `start` och `stop` är en integral multipel av `step`; det vill säga att intervallet inkluderas i båda ändar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="8dffe-198">Under vissa två `Int` uttryck `start` och `stop`är `start .. stop` ett intervall uttryck som är lika med `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="8dffe-199">Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start`; i sådana fall är intervallet tomt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="8dffe-200">Några exempel intervall är:</span><span class="sxs-lookup"><span data-stu-id="8dffe-200">Some example ranges are:</span></span>

- <span data-ttu-id="8dffe-201">`1..3` är intervallet 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="8dffe-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="8dffe-202">`2..2..5` är intervallet 2, 4.</span><span class="sxs-lookup"><span data-stu-id="8dffe-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="8dffe-203">`2..2..6` är intervallet 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="8dffe-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="8dffe-204">`6..-2..2` är intervallet 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="8dffe-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="8dffe-205">`2..1` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="8dffe-206">`2..6..7` är intervallet 2.</span><span class="sxs-lookup"><span data-stu-id="8dffe-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="8dffe-207">`2..2..1` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="8dffe-208">`1..-1..2` är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="8dffe-209">Anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-209">Callable Expressions</span></span>

<span data-ttu-id="8dffe-210">En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.</span><span class="sxs-lookup"><span data-stu-id="8dffe-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="8dffe-211">`X` är till exempel en åtgärds-literal som refererar till standard biblioteket `X`-åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="8dffe-212">Om en åtgärd stöder `Adjoint` Functor är `Adjoint op` ett åtgärds uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="8dffe-213">På samma sätt, om åtgärden har stöd för `Controlled` Functor, är `Controlled op` ett åtgärds uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="8dffe-214">Typerna av dessa uttryck anges i [Functors](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="8dffe-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="8dffe-215">Functors (`Adjoint` och `Controlled`) binder mer nära varandra än alla andra operatorer, förutom unwrap-operatorn `!` och mat ris indexering med `[]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="8dffe-216">Därför är följande alla juridiska, förutsatt att de åtgärder som har stöd för de functors som används:</span><span class="sxs-lookup"><span data-stu-id="8dffe-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="8dffe-217">En anrops bara literal kan användas som ett värde, t. ex. tilldela en variabel eller skicka till ett annat anrop.</span><span class="sxs-lookup"><span data-stu-id="8dffe-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="8dffe-218">I det här fallet, om anropet har typ parametrar, måste de anges som en del av det anropade värdet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="8dffe-219">Ett anrops bara värde kan inte ha ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="8dffe-220">Om `Fun` till exempel är en funktion med signatur `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="8dffe-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="8dffe-221">Anrops anrops anrops uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="8dffe-222">Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="8dffe-223">Typen av anrops uttryck är utdatatypen för den anropande signaturen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="8dffe-224">Om `Op` till exempel är en åtgärd med signatur `((Int, Qubit) => Double)`, är `Op(3, qubit1)` ett uttryck av typen `Double`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="8dffe-225">På samma sätt är `Sin(0.1)` ett uttryck av typen `Double`om `Sin` är en funktion med signatur `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="8dffe-226">Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))`, är `Builder(3)` en funktion från till int.</span><span class="sxs-lookup"><span data-stu-id="8dffe-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="8dffe-227">Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="8dffe-228">För att anropa resultatet av att anropa `Builder` från föregående stycke är därför rätt syntax:</span><span class="sxs-lookup"><span data-stu-id="8dffe-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="8dffe-229">När du anropar en typ-parameter som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="8dffe-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="8dffe-230">Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.</span><span class="sxs-lookup"><span data-stu-id="8dffe-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="8dffe-231">Det krävs för partiellt program (se nedan) om ett argument av typen-parameter lämnas ospecificerat.</span><span class="sxs-lookup"><span data-stu-id="8dffe-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="8dffe-232">Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="8dffe-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="8dffe-233">Om `Func` till exempel har signatur `('T1, 'T2, 'T1) -> 'T2`, `Op1` och `Op2` ha signatur `(Qubit[] => Unit is Adj)`, och `Op3` har signatur `(Qubit[] => Unit)`, för att anropa `Func` med `Op1` som det första argumentet `Op2` som det andra och `Op3` som tredje:</span><span class="sxs-lookup"><span data-stu-id="8dffe-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="8dffe-234">Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="8dffe-235">Partiellt program</span><span class="sxs-lookup"><span data-stu-id="8dffe-235">Partial Application</span></span>

<span data-ttu-id="8dffe-236">Med ett anrops bara uttryck kan ett nytt anropas genom att tillhandahålla en delmängd av argumenten för anropet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="8dffe-237">Detta kallas _delvis program_.</span><span class="sxs-lookup"><span data-stu-id="8dffe-237">This is called _partial application_.</span></span>

<span data-ttu-id="8dffe-238">I Q # uttrycks en delvis tillämpad anrops begränsning genom att ett normalt anrops uttryck skrivs, men med ett under streck `_`för de ospecificerade argumenten.</span><span class="sxs-lookup"><span data-stu-id="8dffe-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="8dffe-239">Det resulterande anropet har samma resultat typ som bas anropet och samma specialisering för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8dffe-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="8dffe-240">Indatatypen för det partiella programmet är helt enkelt den ursprungliga typen med de angivna argumenten borttagna.</span><span class="sxs-lookup"><span data-stu-id="8dffe-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="8dffe-241">Om en föränderligt-variabel skickas som ett angivet argument när du skapar ett partiellt program, används det aktuella värdet för variabeln.</span><span class="sxs-lookup"><span data-stu-id="8dffe-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="8dffe-242">Att ändra värdet för variabeln efteråt påverkar inte den partiella applikationen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="8dffe-243">Om `Op` exempelvis har typen `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="8dffe-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="8dffe-244">`Op(5,(_,_))` har en typ `(((Qubit,Qubit), Double) => Unit is Adj)`, och därför har `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="8dffe-245">`Op(_,(_,1.0))` har typen `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="8dffe-246">`Op(_,((q1,q2),_))` har typen `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="8dffe-247">Observera att vi har använt singleton tuple-motsvarighet här.</span><span class="sxs-lookup"><span data-stu-id="8dffe-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="8dffe-248">Om det delvis använda anropet har typ parametrar som inte kan härledas av kompilatorn, måste de tillhandahållas på anrops platsen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="8dffe-249">Det partiella programmet kan inte ha några ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="8dffe-250">Om `Op` exempelvis har typen `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="8dffe-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="8dffe-251">Rekursion</span><span class="sxs-lookup"><span data-stu-id="8dffe-251">Recursion</span></span>

<span data-ttu-id="8dffe-252">Q # callables kan vara direkt eller indirekt rekursivt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="8dffe-253">Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8dffe-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="8dffe-254">Det finns två viktiga kommentarer om användningen av rekursion, men:</span><span class="sxs-lookup"><span data-stu-id="8dffe-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="8dffe-255">Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="8dffe-256">Detta kan ha en betydande inverkan på körnings tiden för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="8dffe-257">Vid körning på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="8dffe-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="8dffe-258">I synnerhet identifierar inte Q #-kompilatorn och körnings miljön och optimerar slut rekursion.</span><span class="sxs-lookup"><span data-stu-id="8dffe-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="8dffe-259">Tuple-uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-259">Tuple Expressions</span></span>

<span data-ttu-id="8dffe-260">En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges av `(` och `)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="8dffe-261">Till exempel är `(1, One)` ett `(Int, Result)` uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="8dffe-262">Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.</span><span class="sxs-lookup"><span data-stu-id="8dffe-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="8dffe-263">Användardefinierade typ uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="8dffe-264">En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.</span><span class="sxs-lookup"><span data-stu-id="8dffe-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="8dffe-265">Om `IntPair` exempelvis är en användardefinierad typ som baseras på `(Int, Int)`, är `IntPair(2,3)` en giltig litteral av den typen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="8dffe-266">Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.</span><span class="sxs-lookup"><span data-stu-id="8dffe-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="8dffe-267">Packa upp uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-267">Unwrap Expressions</span></span>

<span data-ttu-id="8dffe-268">I Q # är unwrap-operatorn ett avslutande utrops tecken `!`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="8dffe-269">Om `IntPair` till exempel är en användardefinierad typ med underliggande typ `(Int, Int)`och `s` var en variabel med värde `IntPair(2,3)`, är `s!` `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="8dffe-270">För användardefinierade typer definieras i termer av andra användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="8dffe-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="8dffe-271">den avbrytande operatorn kan upprepas. `s!!` anger till exempel det dubblerade omslutna värdet för `s`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="8dffe-272">Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair`och `t` är en variabel med värde `WrappedPair(IntPair(1,2))`, är `t!!` `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="8dffe-273">`!` operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.</span><span class="sxs-lookup"><span data-stu-id="8dffe-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="8dffe-274">`!` och `[]` binda positions läge; det vill säga `a[i]![3]` bör läsas som `((a[i])!)[3]`: ta `i`i `a`, packa upp den och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).</span><span class="sxs-lookup"><span data-stu-id="8dffe-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="8dffe-275">Prioriteten hos `!` operatören har en effekt som kanske inte är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="8dffe-276">Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.</span><span class="sxs-lookup"><span data-stu-id="8dffe-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="8dffe-277">Några exempel:</span><span class="sxs-lookup"><span data-stu-id="8dffe-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="8dffe-278">Mat ris uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-278">Array Expressions</span></span>

<span data-ttu-id="8dffe-279">En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som omges av `[` och `]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="8dffe-280">Alla element måste vara kompatibla med samma typ.</span><span class="sxs-lookup"><span data-stu-id="8dffe-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="8dffe-281">Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.</span><span class="sxs-lookup"><span data-stu-id="8dffe-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="8dffe-282">Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="8dffe-283">Till exempel, om `Op1`, `Op2`och `Op3` alla är `Qubit[] => Unit`, men `Op1` har stöd för `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="8dffe-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="8dffe-284">`[Op1, Op2]` är en matris med `(Qubit[] => Unit)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8dffe-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="8dffe-285">`[Op1, Op3]` är en matris med `(Qubit[] => Unit is Adj)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8dffe-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="8dffe-286">`[Op2, Op3]` är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8dffe-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="8dffe-287">Tomma mat ris strängar, `[]`, tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="8dffe-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="8dffe-288">I stället med `new ★[0]`, där `★` är plats hållare för en lämplig typ, kan du skapa den önskade matrisen med längden noll.</span><span class="sxs-lookup"><span data-stu-id="8dffe-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="8dffe-289">Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="8dffe-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="8dffe-290">`[1,2,3] + [4,5,6]` till exempel `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="8dffe-291">Skapa matris</span><span class="sxs-lookup"><span data-stu-id="8dffe-291">Array Creation</span></span>

<span data-ttu-id="8dffe-292">Med en typ och ett `Int` uttryck kan `new` operatören användas för att allokera en ny matris med den aktuella storleken.</span><span class="sxs-lookup"><span data-stu-id="8dffe-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="8dffe-293">`new Int[i+1]` skulle till exempel allokera en ny `Int` matris med `i+1` element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="8dffe-294">Elementen i en ny matris initieras till ett typ beroende standardvärde.</span><span class="sxs-lookup"><span data-stu-id="8dffe-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="8dffe-295">I de flesta fall är detta en variation på noll.</span><span class="sxs-lookup"><span data-stu-id="8dffe-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="8dffe-296">Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.</span><span class="sxs-lookup"><span data-stu-id="8dffe-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="8dffe-297">Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.</span><span class="sxs-lookup"><span data-stu-id="8dffe-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="8dffe-298">Detta liknar en null-referens i språk som C# eller Java.</span><span class="sxs-lookup"><span data-stu-id="8dffe-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="8dffe-299">Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="8dffe-300">Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="8dffe-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="8dffe-301">Standardvärdena för varje typ är:</span><span class="sxs-lookup"><span data-stu-id="8dffe-301">The default values for each type are:</span></span>

<span data-ttu-id="8dffe-302">Typ</span><span class="sxs-lookup"><span data-stu-id="8dffe-302">Type</span></span> | <span data-ttu-id="8dffe-303">Standard</span><span class="sxs-lookup"><span data-stu-id="8dffe-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="8dffe-304">_Ogiltig qubit_</span><span class="sxs-lookup"><span data-stu-id="8dffe-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="8dffe-305">Det tomma intervallet `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="8dffe-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="8dffe-306">_Ogiltigt anrops bara_</span><span class="sxs-lookup"><span data-stu-id="8dffe-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="8dffe-307">Tuple-typer är initierade element-by-element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="8dffe-308">Ojämna matriser</span><span class="sxs-lookup"><span data-stu-id="8dffe-308">Jagged Arrays</span></span>

<span data-ttu-id="8dffe-309">En taggad matris, som ibland kallas matriser, är en matris vars element är matriser.</span><span class="sxs-lookup"><span data-stu-id="8dffe-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="8dffe-310">Elementen i en taggad matris kan ha olika storlekar.</span><span class="sxs-lookup"><span data-stu-id="8dffe-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="8dffe-311">I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.</span><span class="sxs-lookup"><span data-stu-id="8dffe-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="8dffe-312">Mat ris segment</span><span class="sxs-lookup"><span data-stu-id="8dffe-312">Array Slices</span></span>

<span data-ttu-id="8dffe-313">Med ett mat ris uttryck och ett `Range` uttryck kan ett nytt uttryck skapas med hjälp av operatorn `[` och `]` matris.</span><span class="sxs-lookup"><span data-stu-id="8dffe-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="8dffe-314">Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen i `Range`, i den ordning som definieras av `Range`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="8dffe-315">Om `a` till exempel är kopplat till en matris med `Double`s, är `a[3..-1..0]` ett `Double[]`-uttryck som innehåller de fyra första elementen i `a`, men i omvänd ordning som de visas i `a`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="8dffe-316">Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.</span><span class="sxs-lookup"><span data-stu-id="8dffe-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="8dffe-317">Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att kunna segmentera.</span><span class="sxs-lookup"><span data-stu-id="8dffe-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="8dffe-318">Om till exempel `a` och `b` båda matriserna för `Int`s, uttrycks en sektor från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="8dffe-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="8dffe-319">Alla matriser i Q # är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="8dffe-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="8dffe-320">Det vill säga det första elementet i en matris `a` alltid `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="8dffe-321">Från och med vår 0,8-utgåva stöder vi sammanhangsbaserade uttryck för intervall segmentering.</span><span class="sxs-lookup"><span data-stu-id="8dffe-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="8dffe-322">I synnerhet kan intervall start-och slut värden utelämnas i kontexten för ett intervall segment uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="8dffe-323">I så fall kommer kompileraren att tillämpa följande regler för att härleda de avsedda avgränsarna för intervallet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="8dffe-324">Om start värde för intervall t. ex. utelämnas används värdet för uppskjutet start värde</span><span class="sxs-lookup"><span data-stu-id="8dffe-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="8dffe-325">är noll om inget steg har angetts eller det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="8dffe-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="8dffe-326">är längden på den segmenterade matrisen minus en om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="8dffe-327">Om slutvärdet för intervallet utelämnas visas värdet för det härledda slut värdet</span><span class="sxs-lookup"><span data-stu-id="8dffe-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="8dffe-328">är längden på den segmenterade matrisen minus ett om inget steg har angetts eller om det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="8dffe-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="8dffe-329">är noll om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="8dffe-330">Uttryck för mat ris element</span><span class="sxs-lookup"><span data-stu-id="8dffe-330">Array Element Expressions</span></span>

<span data-ttu-id="8dffe-331">Med ett mat ris uttryck och ett `Int` uttryck kan ett nytt uttryck skapas med hjälp av operatorn `[` och `]` mat ris element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="8dffe-332">Det nya uttrycket är av samma typ som matrisens element typ.</span><span class="sxs-lookup"><span data-stu-id="8dffe-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="8dffe-333">Om `a` till exempel är kopplat till en matris med `Double`s är `a[4]` ett `Double`-uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="8dffe-334">Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.</span><span class="sxs-lookup"><span data-stu-id="8dffe-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="8dffe-335">Om till exempel `a` och `b` båda matriserna för `Int`s, uttrycks ett element från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="8dffe-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="8dffe-336">Alla matriser i Q # är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="8dffe-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="8dffe-337">Det vill säga det första elementet i en matris `a` alltid `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="8dffe-338">Kopiera och uppdatera uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="8dffe-339">Nya matriser kan skapas från befintliga med hjälp av kopierings-och-uppdatera-uttryck.</span><span class="sxs-lookup"><span data-stu-id="8dffe-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="8dffe-340">Ett kopierings-och-uppdatering-uttryck är ett uttryck i formuläret `expression1 w/ expression2 <- expression3`, där `expression1` måste vara av typen `T[]` för viss typ `T`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="8dffe-341">Den andra `expression2` definierar indexen för elementen som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen `Range`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="8dffe-342">Om `expression2` är av typen `Int`måste `expression3` vara av typen `T`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="8dffe-343">Om `expression2` är av typen `Range`måste `expression3` vara av typen `T[]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="8dffe-344">Ett kopierings-och-uppdatera-uttryck `arr w/ idx <- value` skapar en ny matris med alla element som anges till motsvarande-element i `arr`, förutom elementen på `idx`, som är inställda på en/ett (a) `value`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="8dffe-345">Om `arr` till exempel innehåller en matris `[0,1,2,3]`</span><span class="sxs-lookup"><span data-stu-id="8dffe-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="8dffe-346">`arr w/ 0 <- 10` är matrisen `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="8dffe-347">`arr w/ 2 <- 10` är matrisen `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="8dffe-348">`arr w/ 0..2..3 <- [10,12]` är matrisen `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="8dffe-349">Det finns liknande uttryck för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="8dffe-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="8dffe-350">Överväg till exempel typen</span><span class="sxs-lookup"><span data-stu-id="8dffe-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="8dffe-351">Om `c` innehåller värdet av typen `Complex(1.,-1.)`, är `c w/ Re <- 0.` ett uttryck av typen `Complex` som utvärderas till `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="8dffe-352">Villkors uttryck</span><span class="sxs-lookup"><span data-stu-id="8dffe-352">Conditional Expressions</span></span>

<span data-ttu-id="8dffe-353">Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="8dffe-354">`a==b ? c | d`till exempel.</span><span class="sxs-lookup"><span data-stu-id="8dffe-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="8dffe-355">I det här exemplet kommer värdet för villkors uttrycket att `c` om `a==b` är sant och `d` om det är falskt.</span><span class="sxs-lookup"><span data-stu-id="8dffe-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="8dffe-356">De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.</span><span class="sxs-lookup"><span data-stu-id="8dffe-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="8dffe-357">I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.</span><span class="sxs-lookup"><span data-stu-id="8dffe-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="8dffe-358">Till exempel, om `Op1`, `Op2`och `Op3` alla är `Qubit[]=>Unit`, men `Op1` har stöd för `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="8dffe-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="8dffe-359">`flag ? Op1 | Op2` är en `(Qubit[] => Unit)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8dffe-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="8dffe-360">`flag ? Op1 | Op3` är en `(Qubit[] => Unit is Adj)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8dffe-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="8dffe-361">`flag ? Op2 | Op3` är en `(Qubit[] => Unit is Ctl)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8dffe-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="8dffe-362">Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.</span><span class="sxs-lookup"><span data-stu-id="8dffe-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="8dffe-363">Om `a==b` till exempel är sant, i fallet `a==b ? C(qs) | D(qs)`, om är sant, anropas `C`-åtgärden och om den är false anropas bara `D`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="8dffe-364">Detta liknar korta kretsar på andra språk.</span><span class="sxs-lookup"><span data-stu-id="8dffe-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="8dffe-365">Prioritet för Operator</span><span class="sxs-lookup"><span data-stu-id="8dffe-365">Operator Precedence</span></span>

<span data-ttu-id="8dffe-366">Alla binära operatorer är rätt associerade, förutom för `^`.</span><span class="sxs-lookup"><span data-stu-id="8dffe-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="8dffe-367">Hakparenteser, `[` och `]`, för matris-och indexering av matriser, bind före valfri operator.</span><span class="sxs-lookup"><span data-stu-id="8dffe-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="8dffe-368">Functors-`Adjoint` och `Controlled`-bindning efter mat ris indexering men före alla andra operatorer.</span><span class="sxs-lookup"><span data-stu-id="8dffe-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="8dffe-369">Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.</span><span class="sxs-lookup"><span data-stu-id="8dffe-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="8dffe-370">Operatorer i prioritetsordning, från högsta till lägsta:</span><span class="sxs-lookup"><span data-stu-id="8dffe-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="8dffe-371">Operator</span><span class="sxs-lookup"><span data-stu-id="8dffe-371">Operator</span></span> | <span data-ttu-id="8dffe-372">Ariteten</span><span class="sxs-lookup"><span data-stu-id="8dffe-372">Arity</span></span> | <span data-ttu-id="8dffe-373">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8dffe-373">Description</span></span> | <span data-ttu-id="8dffe-374">Operands typer</span><span class="sxs-lookup"><span data-stu-id="8dffe-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="8dffe-375">efterföljande `!`</span><span class="sxs-lookup"><span data-stu-id="8dffe-375">trailing `!`</span></span> | <span data-ttu-id="8dffe-376">Operator</span><span class="sxs-lookup"><span data-stu-id="8dffe-376">Unary</span></span> | <span data-ttu-id="8dffe-377">Packa upp</span><span class="sxs-lookup"><span data-stu-id="8dffe-377">Unwrap</span></span> | <span data-ttu-id="8dffe-378">Valfri användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="8dffe-378">Any user-defined type</span></span>
 <span data-ttu-id="8dffe-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="8dffe-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="8dffe-380">Operator</span><span class="sxs-lookup"><span data-stu-id="8dffe-380">Unary</span></span> | <span data-ttu-id="8dffe-381">Numeriskt negativ, bitvis komplement, logisk negation</span><span class="sxs-lookup"><span data-stu-id="8dffe-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="8dffe-382">`Int`, `BigInt` eller `Double` för `-`, `Int` eller `BigInt` för `~~~`, `Bool` för `not`</span><span class="sxs-lookup"><span data-stu-id="8dffe-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="8dffe-383">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-383">Binary</span></span> | <span data-ttu-id="8dffe-384">Heltals effekt</span><span class="sxs-lookup"><span data-stu-id="8dffe-384">Integer power</span></span> | <span data-ttu-id="8dffe-385">`Int` eller `BigInt` för basen `Int` för exponenten</span><span class="sxs-lookup"><span data-stu-id="8dffe-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="8dffe-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="8dffe-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="8dffe-387">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-387">Binary</span></span> | <span data-ttu-id="8dffe-388">Division, multiplikation, heltals-modulus</span><span class="sxs-lookup"><span data-stu-id="8dffe-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="8dffe-389">`Int`, `BigInt` eller `Double` för `/` och `*`, `Int` eller `BigInt` för `%`</span><span class="sxs-lookup"><span data-stu-id="8dffe-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="8dffe-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="8dffe-390">`+`, `-`</span></span> | <span data-ttu-id="8dffe-391">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-391">Binary</span></span> | <span data-ttu-id="8dffe-392">Kombination av addition eller sträng och matris, subtraktion</span><span class="sxs-lookup"><span data-stu-id="8dffe-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="8dffe-393">`Int`, `BigInt` eller `Double`, även `String` eller valfri mat ris typ för `+`</span><span class="sxs-lookup"><span data-stu-id="8dffe-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="8dffe-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="8dffe-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="8dffe-395">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-395">Binary</span></span> | <span data-ttu-id="8dffe-396">Vänster SKIFT, höger Skift</span><span class="sxs-lookup"><span data-stu-id="8dffe-396">Left shift, right shift</span></span> | <span data-ttu-id="8dffe-397">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8dffe-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="8dffe-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="8dffe-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="8dffe-399">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-399">Binary</span></span> | <span data-ttu-id="8dffe-400">Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="8dffe-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="8dffe-401">`Int`, `BigInt` eller `Double`</span><span class="sxs-lookup"><span data-stu-id="8dffe-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="8dffe-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="8dffe-402">`==`, `!=`</span></span> | <span data-ttu-id="8dffe-403">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-403">Binary</span></span> | <span data-ttu-id="8dffe-404">lika med, inte lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="8dffe-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="8dffe-405">vilken primitiv typ som helst</span><span class="sxs-lookup"><span data-stu-id="8dffe-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="8dffe-406">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-406">Binary</span></span> | <span data-ttu-id="8dffe-407">Bitvis och</span><span class="sxs-lookup"><span data-stu-id="8dffe-407">Bitwise AND</span></span> | <span data-ttu-id="8dffe-408">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8dffe-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="8dffe-409">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-409">Binary</span></span> | <span data-ttu-id="8dffe-410">Bitvis XOR</span><span class="sxs-lookup"><span data-stu-id="8dffe-410">Bitwise XOR</span></span> | <span data-ttu-id="8dffe-411">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8dffe-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="8dffe-412">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-412">Binary</span></span> | <span data-ttu-id="8dffe-413">Bitvis eller</span><span class="sxs-lookup"><span data-stu-id="8dffe-413">Bitwise OR</span></span> | <span data-ttu-id="8dffe-414">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8dffe-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="8dffe-415">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-415">Binary</span></span> | <span data-ttu-id="8dffe-416">Logiska och</span><span class="sxs-lookup"><span data-stu-id="8dffe-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="8dffe-417">Binär</span><span class="sxs-lookup"><span data-stu-id="8dffe-417">Binary</span></span> | <span data-ttu-id="8dffe-418">Logiska eller</span><span class="sxs-lookup"><span data-stu-id="8dffe-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="8dffe-419">Binär/ternär</span><span class="sxs-lookup"><span data-stu-id="8dffe-419">Binary/Ternary</span></span> | <span data-ttu-id="8dffe-420">Intervall operator</span><span class="sxs-lookup"><span data-stu-id="8dffe-420">Range operator</span></span> | `Int`
 <span data-ttu-id="8dffe-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="8dffe-421">`?` `|`</span></span> | <span data-ttu-id="8dffe-422">Ternär</span><span class="sxs-lookup"><span data-stu-id="8dffe-422">Ternary</span></span> | <span data-ttu-id="8dffe-423">Villkorsstyrd</span><span class="sxs-lookup"><span data-stu-id="8dffe-423">Conditional</span></span> | <span data-ttu-id="8dffe-424">`Bool` för den vänstra sidan</span><span class="sxs-lookup"><span data-stu-id="8dffe-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="8dffe-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="8dffe-425">`w/` `<-`</span></span> | <span data-ttu-id="8dffe-426">Ternär</span><span class="sxs-lookup"><span data-stu-id="8dffe-426">Ternary</span></span> | <span data-ttu-id="8dffe-427">Kopiera och uppdatera</span><span class="sxs-lookup"><span data-stu-id="8dffe-427">Copy-and-update</span></span> | <span data-ttu-id="8dffe-428">Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="8dffe-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
