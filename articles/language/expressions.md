---
title: 'Q # uttryck'
description: 'Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683930"
---
# <a name="expressions"></a><span data-ttu-id="69c93-103">Uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="69c93-104">Baserat</span><span class="sxs-lookup"><span data-stu-id="69c93-104">Grouping</span></span>

<span data-ttu-id="69c93-105">Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="69c93-106">`(7)` `Int` Är till exempel ett uttryck, `([1,2,3])` är ett uttryck av typen matris för `Int`s och `((1,2))` är ett uttryck med typen. `(Int, Int)`</span><span class="sxs-lookup"><span data-stu-id="69c93-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="69c93-107">Motsvarigheten mellan enkla värden och tupler med ett enda element som beskrivs i [typ modellen](xref:microsoft.quantum.language.type-model#tuple-types) tar bort tvetydigheten `(6)` mellan som en grupp `(6)` och som en tupel med ett enda element.</span><span class="sxs-lookup"><span data-stu-id="69c93-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="69c93-108">Symboler</span><span class="sxs-lookup"><span data-stu-id="69c93-108">Symbols</span></span>

<span data-ttu-id="69c93-109">Namnet på en symbol som är kopplad till ett värde av typen `'T` är ett uttryck av typen. `'T`</span><span class="sxs-lookup"><span data-stu-id="69c93-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="69c93-110">Om symbolen `count` till exempel är kopplad till heltal svärdet `5` `count` är ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="69c93-111">Numeriska uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-111">Numeric Expressions</span></span>

<span data-ttu-id="69c93-112">Numeriska uttryck är uttryck av typen `Int`, `BigInt`eller `Double`.</span><span class="sxs-lookup"><span data-stu-id="69c93-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="69c93-113">Det vill säga att de är antingen heltals-eller flytt ALS nummer.</span><span class="sxs-lookup"><span data-stu-id="69c93-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="69c93-114">`Int`litteraler i Q # är identiska med heltals strängar i C#, förutom att ingen efterföljande "l" eller "L" krävs (eller tillåts).</span><span class="sxs-lookup"><span data-stu-id="69c93-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="69c93-115">Hexadecimala och binära heltal stöds med prefixet "0x" och "0b".</span><span class="sxs-lookup"><span data-stu-id="69c93-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="69c93-116">`BigInt`litteraler i Q # är identiska med Big heltals strängar i .NET, med ett efterföljande "l" eller "L".</span><span class="sxs-lookup"><span data-stu-id="69c93-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="69c93-117">Hexadecimala Big heltal stöds med ett "0x"-prefix.</span><span class="sxs-lookup"><span data-stu-id="69c93-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="69c93-118">Det innebär att följande är giltig användning av `BigInt` litteraler:</span><span class="sxs-lookup"><span data-stu-id="69c93-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="69c93-119">`Double`litteraler i Q # är identiska med dubbel litteraler i C#, förutom att ingen efterföljande "d" eller "D" krävs (eller tillåts).</span><span class="sxs-lookup"><span data-stu-id="69c93-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="69c93-120">Med ett mat ris uttryck för valfri element typ kan `Int` ett uttryck skapas med hjälp av `Length` den inbyggda funktionen, med mat ris uttrycket omslutna i parentes `(` och. `)`</span><span class="sxs-lookup"><span data-stu-id="69c93-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="69c93-121">Om `a` till exempel är kopplat till en matris, `Length(a)` är ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="69c93-122">Om `b` är `Int[][]`en matris med heltals `Length(b)` matriser, är antalet underordnade matriser i `b`och `Length(b[1])` är antalet heltal i den andra under matrisen i. `b`</span><span class="sxs-lookup"><span data-stu-id="69c93-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="69c93-123">Två numeriska uttryck av samma typ, de binära operatorerna `+`, `-`, `*`och `/` kan användas för att skapa ett nytt numeriskt uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="69c93-124">Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="69c93-125">Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="69c93-126">På samma sätt `^` kan användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="69c93-127">Slutligen `^` kan du använda ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="69c93-128">I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="69c93-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="69c93-129">Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big- `%` heltals uttryck skapas `&&&` med operatörerna (Modulus `|||` ), (BITVIS and) `^^^` , (bitvis or) eller (Bitvis XOR).</span><span class="sxs-lookup"><span data-stu-id="69c93-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="69c93-130">Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till `<<<` höger, kan operatorerna ( `>>>` aritmetisk vänster Shift) eller (aritmetiska höger Shift) användas för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="69c93-131">Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.</span><span class="sxs-lookup"><span data-stu-id="69c93-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="69c93-132">Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="69c93-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="69c93-133">Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet `mod 64`. det vill säga en skift på 1 och en förskjutning på 65 har samma resultat.</span><span class="sxs-lookup"><span data-stu-id="69c93-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="69c93-134">För både heltals-och Big heltals värden är skiften aritmetiska.</span><span class="sxs-lookup"><span data-stu-id="69c93-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="69c93-135">Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="69c93-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="69c93-136">Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.</span><span class="sxs-lookup"><span data-stu-id="69c93-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="69c93-137">Heltals Division och heltals-Modulus följer samma beteende för negativa tal som C#.</span><span class="sxs-lookup"><span data-stu-id="69c93-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="69c93-138">Det `a % b` vill säga har alltid samma signera som `a`och `b * (a / b) + a % b` är alltid lika med. `a`</span><span class="sxs-lookup"><span data-stu-id="69c93-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="69c93-139">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="69c93-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="69c93-140">5</span><span class="sxs-lookup"><span data-stu-id="69c93-140">5</span></span> | <span data-ttu-id="69c93-141">2</span><span class="sxs-lookup"><span data-stu-id="69c93-141">2</span></span> | <span data-ttu-id="69c93-142">2</span><span class="sxs-lookup"><span data-stu-id="69c93-142">2</span></span> | <span data-ttu-id="69c93-143">1</span><span class="sxs-lookup"><span data-stu-id="69c93-143">1</span></span>
 <span data-ttu-id="69c93-144">5</span><span class="sxs-lookup"><span data-stu-id="69c93-144">5</span></span> | <span data-ttu-id="69c93-145">-2</span><span class="sxs-lookup"><span data-stu-id="69c93-145">-2</span></span> | <span data-ttu-id="69c93-146">-2</span><span class="sxs-lookup"><span data-stu-id="69c93-146">-2</span></span> | <span data-ttu-id="69c93-147">1</span><span class="sxs-lookup"><span data-stu-id="69c93-147">1</span></span>
 <span data-ttu-id="69c93-148">-5</span><span class="sxs-lookup"><span data-stu-id="69c93-148">-5</span></span> | <span data-ttu-id="69c93-149">2</span><span class="sxs-lookup"><span data-stu-id="69c93-149">2</span></span> | <span data-ttu-id="69c93-150">-2</span><span class="sxs-lookup"><span data-stu-id="69c93-150">-2</span></span> | <span data-ttu-id="69c93-151">-1</span><span class="sxs-lookup"><span data-stu-id="69c93-151">-1</span></span>
 <span data-ttu-id="69c93-152">-5</span><span class="sxs-lookup"><span data-stu-id="69c93-152">-5</span></span> | <span data-ttu-id="69c93-153">-2</span><span class="sxs-lookup"><span data-stu-id="69c93-153">-2</span></span> | <span data-ttu-id="69c93-154">2</span><span class="sxs-lookup"><span data-stu-id="69c93-154">2</span></span> | <span data-ttu-id="69c93-155">-1</span><span class="sxs-lookup"><span data-stu-id="69c93-155">-1</span></span>

<span data-ttu-id="69c93-156">Big Integer-Division och Modulus fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="69c93-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="69c93-157">Ett nytt uttryck kan skapas med hjälp av ett numeriskt uttryck med `-` hjälp av den unära operatorn.</span><span class="sxs-lookup"><span data-stu-id="69c93-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="69c93-158">Det nya uttrycket är av samma typ som komponent uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="69c93-159">Med alla heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med `~~~` den unära operatorn (bitvis komplement).</span><span class="sxs-lookup"><span data-stu-id="69c93-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="69c93-160">Booleska uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-160">Boolean Expressions</span></span>

<span data-ttu-id="69c93-161">De två `Bool` literala värdena `true` är `false`och.</span><span class="sxs-lookup"><span data-stu-id="69c93-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="69c93-162">Om du har två uttryck av samma primitiva typ kan `==` de `!=` och binära operatorerna användas för att `Bool` skapa ett uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="69c93-163">Uttrycket är sant om de två uttrycken är lika och falskt om inte.</span><span class="sxs-lookup"><span data-stu-id="69c93-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="69c93-164">Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras.</span><span class="sxs-lookup"><span data-stu-id="69c93-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="69c93-165">Du kan till exempel använda operatorn `!` "unwrap" (förklaras på sidan för [Q # typ modell](xref:microsoft.quantum.language.type-model#user-defined-types)).</span><span class="sxs-lookup"><span data-stu-id="69c93-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="69c93-166">Likhets jämförelse `Qubit` för värden är identitets likhet; det vill säga om de två uttrycken identifierar samma qubit.</span><span class="sxs-lookup"><span data-stu-id="69c93-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="69c93-167">Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="69c93-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="69c93-168">Jämförelse av `Double` värden kan vara missvisande på grund av avrundnings effekter.</span><span class="sxs-lookup"><span data-stu-id="69c93-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="69c93-169">Till exempel `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="69c93-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="69c93-170">Två numeriska uttryck, de binära operatorerna `>` `<` `>=`,, och `<=` kan användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="69c93-171">Med två booleska uttryck kan de `and` och `or` binära operatorerna användas för att skapa ett nytt booleskt uttryck som är sant om båda uttrycken (ansvars båda eller båda) är sanna.</span><span class="sxs-lookup"><span data-stu-id="69c93-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="69c93-172">Med alla booleska uttryck kan den `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.</span><span class="sxs-lookup"><span data-stu-id="69c93-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="69c93-173">Sträng uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-173">String Expressions</span></span>

<span data-ttu-id="69c93-174">Q # tillåter att strängar används i `fail` instruktionen och `Log` standard funktionen.</span><span class="sxs-lookup"><span data-stu-id="69c93-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="69c93-175">Strängar i Q # är antingen litteraler eller interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="69c93-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="69c93-176">Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode- `"`tecken som omges av dubbla citat tecken.</span><span class="sxs-lookup"><span data-stu-id="69c93-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="69c93-177">I `\` en sträng kan back snedstrecket användas för att undvika ett dubbelt citat tecken och för att infoga en ny rad `\n`som, en vagn retur som `\r`och en flik som. `\t`</span><span class="sxs-lookup"><span data-stu-id="69c93-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="69c93-178">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="69c93-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="69c93-179">Q #-syntaxen för String-interpolation är en delmängd av C# 7,0-syntaxen. Q # stöder inte orda Grant (multi-line) interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="69c93-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="69c93-180">Se [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) för C#-syntaxen.</span><span class="sxs-lookup"><span data-stu-id="69c93-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="69c93-181">Uttryck i en interpolerad sträng följer Q # syntax, inte C#-syntax.</span><span class="sxs-lookup"><span data-stu-id="69c93-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="69c93-182">Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.</span><span class="sxs-lookup"><span data-stu-id="69c93-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="69c93-183">Qubit-uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-183">Qubit Expressions</span></span>

<span data-ttu-id="69c93-184">De enda `Qubit` uttrycken är symboler som är `Qubit` kopplade till värden eller mat `Qubit` ris element.</span><span class="sxs-lookup"><span data-stu-id="69c93-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="69c93-185">Det finns inga `Qubit` litteraler.</span><span class="sxs-lookup"><span data-stu-id="69c93-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="69c93-186">Pauli-uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-186">Pauli Expressions</span></span>

<span data-ttu-id="69c93-187">De fyra `Pauli` värdena, `PauliI`, `PauliX`, `PauliY`och `PauliZ`, är giltiga `Pauli` uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="69c93-188">Förutom så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="69c93-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="69c93-189">Resultat uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-189">Result Expressions</span></span>

<span data-ttu-id="69c93-190">De två `Result` värdena `One` och `Zero`, är giltiga `Result` uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="69c93-191">Förutom så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element `Result` .</span><span class="sxs-lookup"><span data-stu-id="69c93-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="69c93-192">Observera särskilt att `One` inte är detsamma som heltalet `1`och det finns ingen direkt konvertering mellan dem.</span><span class="sxs-lookup"><span data-stu-id="69c93-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="69c93-193">Samma sak gäller `Zero` och `0`.</span><span class="sxs-lookup"><span data-stu-id="69c93-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="69c93-194">Intervall uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-194">Range Expressions</span></span>

<span data-ttu-id="69c93-195">Alla `Int` tre uttryck `start`, `step`, och `stop`, `start .. step .. stop` är ett intervall uttryck vars första element är `start`, det andra elementet är `start+step`, det tredje elementet `start+step+step`, osv., tills `stop` det skickas.</span><span class="sxs-lookup"><span data-stu-id="69c93-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="69c93-196">Ett intervall kan vara tomt om, t. ex `step` . är positivt `stop < start`och.</span><span class="sxs-lookup"><span data-stu-id="69c93-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="69c93-197">Det sista elementet `stop` i intervallet är om skillnaden mellan `start` och `stop` är en integral multipel av; `step` det vill säga att intervallet inkluderas i båda ändar.</span><span class="sxs-lookup"><span data-stu-id="69c93-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="69c93-198">Två `Int` uttryck `start` har angetts och `stop` `start .. stop` är ett intervall uttryck som är lika med `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="69c93-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="69c93-199">Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start`; i sådana fall är intervallet tomt.</span><span class="sxs-lookup"><span data-stu-id="69c93-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="69c93-200">Några exempel intervall är:</span><span class="sxs-lookup"><span data-stu-id="69c93-200">Some example ranges are:</span></span>

- <span data-ttu-id="69c93-201">`1..3`är intervallet 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="69c93-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="69c93-202">`2..2..5`är intervallet 2, 4.</span><span class="sxs-lookup"><span data-stu-id="69c93-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="69c93-203">`2..2..6`är intervallet 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="69c93-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="69c93-204">`6..-2..2`är intervallet 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="69c93-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="69c93-205">`2..1`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="69c93-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="69c93-206">`2..6..7`är intervallet 2.</span><span class="sxs-lookup"><span data-stu-id="69c93-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="69c93-207">`2..2..1`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="69c93-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="69c93-208">`1..-1..2`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="69c93-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="69c93-209">Anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-209">Callable Expressions</span></span>

<span data-ttu-id="69c93-210">En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.</span><span class="sxs-lookup"><span data-stu-id="69c93-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="69c93-211">`X` Är till exempel en åtgärds-literal som refererar till standard biblioteks `X` åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.</span><span class="sxs-lookup"><span data-stu-id="69c93-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="69c93-212">Om en åtgärd har stöd `Adjoint` för Functor `Adjoint op` är ett åtgärds uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="69c93-213">På samma sätt `Controlled op` är det ett åtgärds `Controlled` uttryck om åtgärden stöder Functor.</span><span class="sxs-lookup"><span data-stu-id="69c93-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="69c93-214">Typerna av dessa uttryck anges i [Functors](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="69c93-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="69c93-215">Functors (`Adjoint` och `Controlled`) binder mer nära varandra än alla andra operatorer, förutom unwrap- `!` operatorn och mat ris `[]`indexering med.</span><span class="sxs-lookup"><span data-stu-id="69c93-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="69c93-216">Därför är följande alla juridiska, förutsatt att de åtgärder som har stöd för de functors som används:</span><span class="sxs-lookup"><span data-stu-id="69c93-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="69c93-217">En anrops bara literal kan användas som ett värde, t. ex. tilldela en variabel eller skicka till ett annat anrop.</span><span class="sxs-lookup"><span data-stu-id="69c93-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="69c93-218">I det här fallet, om anropet har typ parametrar, måste de anges som en del av det anropade värdet.</span><span class="sxs-lookup"><span data-stu-id="69c93-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="69c93-219">Ett anrops bara värde kan inte ha ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="69c93-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="69c93-220">Om `Fun` är till exempel en funktion med signatur `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="69c93-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="69c93-221">Anrops anrops anrops uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="69c93-222">Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="69c93-223">Typen av anrops uttryck är utdatatypen för den anropande signaturen.</span><span class="sxs-lookup"><span data-stu-id="69c93-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="69c93-224">Om `Op` är till exempel en åtgärd med signatur `((Int, Qubit) => Double)`, `Op(3, qubit1)` är ett uttryck av typen. `Double`</span><span class="sxs-lookup"><span data-stu-id="69c93-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="69c93-225">På samma sätt, `Sin` om är en funktion med `(Double -> Double)`signatur `Sin(0.1)` , är ett uttryck av `Double`typen.</span><span class="sxs-lookup"><span data-stu-id="69c93-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="69c93-226">Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))`, `Builder(3)` är en funktion från till int.</span><span class="sxs-lookup"><span data-stu-id="69c93-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="69c93-227">Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="69c93-228">För att anropa resultatet av anrop `Builder` från föregående stycke är därför rätt syntax:</span><span class="sxs-lookup"><span data-stu-id="69c93-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="69c93-229">När du anropar en typ-parameter som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="69c93-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="69c93-230">Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.</span><span class="sxs-lookup"><span data-stu-id="69c93-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="69c93-231">Det krävs för partiellt program (se nedan) om ett argument av typen-parameter lämnas ospecificerat.</span><span class="sxs-lookup"><span data-stu-id="69c93-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="69c93-232">Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="69c93-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="69c93-233">Om `Func` har exempelvis signatur `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)`och har signatur, och `Op3` har signatur `(Qubit[] => Unit)`, för att anropa `Func` med `Op1` som första argument, `Op2` som den andra, och `Op3` som tredje:</span><span class="sxs-lookup"><span data-stu-id="69c93-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="69c93-234">Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.</span><span class="sxs-lookup"><span data-stu-id="69c93-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="69c93-235">Partiellt program</span><span class="sxs-lookup"><span data-stu-id="69c93-235">Partial Application</span></span>

<span data-ttu-id="69c93-236">Med ett anrops bara uttryck kan ett nytt anropas genom att tillhandahålla en delmängd av argumenten för anropet.</span><span class="sxs-lookup"><span data-stu-id="69c93-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="69c93-237">Detta kallas _delvis program_.</span><span class="sxs-lookup"><span data-stu-id="69c93-237">This is called _partial application_.</span></span>

<span data-ttu-id="69c93-238">I Q # uttrycks en delvis Använd anrops begränsning genom att skriva ett normalt anrops uttryck, men med ett under `_`streck, för de ospecificerade argumenten.</span><span class="sxs-lookup"><span data-stu-id="69c93-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="69c93-239">Det resulterande anropet har samma resultat typ som bas anropet och samma specialisering för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="69c93-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="69c93-240">Indatatypen för det partiella programmet är helt enkelt den ursprungliga typen med de angivna argumenten borttagna.</span><span class="sxs-lookup"><span data-stu-id="69c93-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="69c93-241">Om en föränderligt-variabel skickas som ett angivet argument när du skapar ett partiellt program, används det aktuella värdet för variabeln.</span><span class="sxs-lookup"><span data-stu-id="69c93-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="69c93-242">Att ändra värdet för variabeln efteråt påverkar inte den partiella applikationen.</span><span class="sxs-lookup"><span data-stu-id="69c93-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="69c93-243">Till exempel om `Op` har typen `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="69c93-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="69c93-244">`Op(5,(_,_))`har typen `(((Qubit,Qubit), Double) => Unit is Adj)`, och därför har `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="69c93-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="69c93-245">`Op(_,(_,1.0))`har typen `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="69c93-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="69c93-246">`Op(_,((q1,q2),_))`har typen `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="69c93-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="69c93-247">Observera att vi har använt singleton tuple-motsvarighet här.</span><span class="sxs-lookup"><span data-stu-id="69c93-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="69c93-248">Om det delvis använda anropet har typ parametrar som inte kan härledas av kompilatorn, måste de tillhandahållas på anrops platsen.</span><span class="sxs-lookup"><span data-stu-id="69c93-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="69c93-249">Det partiella programmet kan inte ha några ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="69c93-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="69c93-250">Till exempel om `Op` har typen `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="69c93-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="69c93-251">Rekursion</span><span class="sxs-lookup"><span data-stu-id="69c93-251">Recursion</span></span>

<span data-ttu-id="69c93-252">Q # callables kan vara direkt eller indirekt rekursivt.</span><span class="sxs-lookup"><span data-stu-id="69c93-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="69c93-253">Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="69c93-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="69c93-254">Det finns två viktiga kommentarer om användningen av rekursion, men:</span><span class="sxs-lookup"><span data-stu-id="69c93-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="69c93-255">Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.</span><span class="sxs-lookup"><span data-stu-id="69c93-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="69c93-256">Detta kan ha en betydande inverkan på körnings tiden för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="69c93-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="69c93-257">Vid körning på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="69c93-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="69c93-258">I synnerhet identifierar inte Q #-kompilatorn och körnings miljön och optimerar slut rekursion.</span><span class="sxs-lookup"><span data-stu-id="69c93-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="69c93-259">Tuple-uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-259">Tuple Expressions</span></span>

<span data-ttu-id="69c93-260">En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges `(` av `)`och.</span><span class="sxs-lookup"><span data-stu-id="69c93-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="69c93-261">`(1, One)` Är till exempel ett `(Int, Result)` uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="69c93-262">Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.</span><span class="sxs-lookup"><span data-stu-id="69c93-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="69c93-263">Användardefinierade typ uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="69c93-264">En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.</span><span class="sxs-lookup"><span data-stu-id="69c93-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="69c93-265">Om `IntPair` är till exempel en användardefinierad typ som baseras på `(Int, Int)`, `IntPair(2,3)` är en giltig litteral av den typen.</span><span class="sxs-lookup"><span data-stu-id="69c93-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="69c93-266">Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.</span><span class="sxs-lookup"><span data-stu-id="69c93-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="69c93-267">Packa upp uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-267">Unwrap Expressions</span></span>

<span data-ttu-id="69c93-268">I Q # är unwrap-operatorn ett avslutande utrops tecken `!`.</span><span class="sxs-lookup"><span data-stu-id="69c93-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="69c93-269">Om `IntPair` är till exempel en användardefinierad typ med underliggande typ `(Int, Int)`och `s` var en variabel med värde `IntPair(2,3)`, `s!` skulle det vara. `(2,3)`</span><span class="sxs-lookup"><span data-stu-id="69c93-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="69c93-270">För användardefinierade typer definieras i termer av andra användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="69c93-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="69c93-271">den avbrytande operatorn kan upprepas. `s!!` anger t. ex. dubblerat-värde för `s`.</span><span class="sxs-lookup"><span data-stu-id="69c93-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="69c93-272">Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair`och `t` är en variabel med värde `WrappedPair(IntPair(1,2))`, `t!!` blir det alltså. `(1,2)`</span><span class="sxs-lookup"><span data-stu-id="69c93-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="69c93-273">`!` Operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.</span><span class="sxs-lookup"><span data-stu-id="69c93-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="69c93-274">`!`och `[]` binda positions läge; det vill säga `a[i]![3]` bör se ut så `((a[i])!)[3]`här: ta `i`elementet "th" `a`, packa upp det och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).</span><span class="sxs-lookup"><span data-stu-id="69c93-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="69c93-275">Prioriteten hos `!` operatorn har en effekt som kanske inte är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="69c93-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="69c93-276">Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.</span><span class="sxs-lookup"><span data-stu-id="69c93-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="69c93-277">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="69c93-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="69c93-278">Mat ris uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-278">Array Expressions</span></span>

<span data-ttu-id="69c93-279">En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som `[` omges av och `]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="69c93-280">Alla element måste vara kompatibla med samma typ.</span><span class="sxs-lookup"><span data-stu-id="69c93-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="69c93-281">Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.</span><span class="sxs-lookup"><span data-stu-id="69c93-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="69c93-282">Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.</span><span class="sxs-lookup"><span data-stu-id="69c93-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="69c93-283">`Op1`Till exempel, `Op2`, och `Op3` alla `Qubit[] => Unit`, men `Op1` stöder `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="69c93-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="69c93-284">`[Op1, Op2]`är en matris med `(Qubit[] => Unit)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="69c93-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="69c93-285">`[Op1, Op3]`är en matris med `(Qubit[] => Unit is Adj)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="69c93-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="69c93-286">`[Op2, Op3]`är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="69c93-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="69c93-287">Tomma mat ris strängar, `[]`tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="69c93-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="69c93-288">I stället `new ★[0]`använda, `★` där är plats hållare för lämplig typ, kan du skapa den önskade matrisen med längden noll.</span><span class="sxs-lookup"><span data-stu-id="69c93-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="69c93-289">Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="69c93-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="69c93-290">Till exempel `[1,2,3] + [4,5,6]` är `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="69c93-291">Skapa matris</span><span class="sxs-lookup"><span data-stu-id="69c93-291">Array Creation</span></span>

<span data-ttu-id="69c93-292">Med en typ och ett `Int` uttryck kan `new` operatorn användas för att allokera en ny matris med den aktuella storleken.</span><span class="sxs-lookup"><span data-stu-id="69c93-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="69c93-293">Allokera till exempel `new Int[i+1]` en ny `Int` matris med `i+1` element.</span><span class="sxs-lookup"><span data-stu-id="69c93-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="69c93-294">Elementen i en ny matris initieras till ett typ beroende standardvärde.</span><span class="sxs-lookup"><span data-stu-id="69c93-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="69c93-295">I de flesta fall är detta en variation på noll.</span><span class="sxs-lookup"><span data-stu-id="69c93-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="69c93-296">Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.</span><span class="sxs-lookup"><span data-stu-id="69c93-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="69c93-297">Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.</span><span class="sxs-lookup"><span data-stu-id="69c93-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="69c93-298">Detta liknar en null-referens i språk som C# eller Java.</span><span class="sxs-lookup"><span data-stu-id="69c93-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="69c93-299">Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="69c93-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="69c93-300">Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="69c93-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="69c93-301">Standardvärdena för varje typ är:</span><span class="sxs-lookup"><span data-stu-id="69c93-301">The default values for each type are:</span></span>

<span data-ttu-id="69c93-302">Typ</span><span class="sxs-lookup"><span data-stu-id="69c93-302">Type</span></span> | <span data-ttu-id="69c93-303">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="69c93-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="69c93-304">_Ogiltig qubit_</span><span class="sxs-lookup"><span data-stu-id="69c93-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="69c93-305">Det tomma intervallet,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="69c93-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="69c93-306">_Ogiltigt anrops bara_</span><span class="sxs-lookup"><span data-stu-id="69c93-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="69c93-307">Tuple-typer är initierade element-by-element.</span><span class="sxs-lookup"><span data-stu-id="69c93-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="69c93-308">Ojämna matriser</span><span class="sxs-lookup"><span data-stu-id="69c93-308">Jagged Arrays</span></span>

<span data-ttu-id="69c93-309">En taggad matris, som ibland kallas matriser, är en matris vars element är matriser.</span><span class="sxs-lookup"><span data-stu-id="69c93-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="69c93-310">Elementen i en taggad matris kan ha olika storlekar.</span><span class="sxs-lookup"><span data-stu-id="69c93-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="69c93-311">I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.</span><span class="sxs-lookup"><span data-stu-id="69c93-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="69c93-312">Mat ris segment</span><span class="sxs-lookup"><span data-stu-id="69c93-312">Array Slices</span></span>

<span data-ttu-id="69c93-313">Med ett mat ris uttryck och `Range` ett uttryck kan ett nytt uttryck skapas med operatorn `[` array `]` och array.</span><span class="sxs-lookup"><span data-stu-id="69c93-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="69c93-314">Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen `Range`i, i den ordning som definieras `Range`av.</span><span class="sxs-lookup"><span data-stu-id="69c93-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="69c93-315">Om `a` till exempel är kopplat till en matris `Double`med s, `a[3..-1..0]` är ett `Double[]` uttryck som innehåller de första fyra elementen i, `a` men i omvänd ordning som de visas i. `a`</span><span class="sxs-lookup"><span data-stu-id="69c93-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="69c93-316">Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.</span><span class="sxs-lookup"><span data-stu-id="69c93-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="69c93-317">Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att kunna segmentera.</span><span class="sxs-lookup"><span data-stu-id="69c93-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="69c93-318">Om `a` till exempel `b` är båda matriserna i `Int`s, uttrycks en sektor från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="69c93-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="69c93-319">Alla matriser i Q # är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="69c93-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="69c93-320">Det vill säga det första elementet i en matris `a` är alltid `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="69c93-321">Från och med vår 0,8-utgåva stöder vi sammanhangsbaserade uttryck för intervall segmentering.</span><span class="sxs-lookup"><span data-stu-id="69c93-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="69c93-322">I synnerhet kan intervall start-och slut värden utelämnas i kontexten för ett intervall segment uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="69c93-323">I så fall kommer kompileraren att tillämpa följande regler för att härleda de avsedda avgränsarna för intervallet.</span><span class="sxs-lookup"><span data-stu-id="69c93-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="69c93-324">Om start värde för intervall t. ex. utelämnas används värdet för uppskjutet start värde</span><span class="sxs-lookup"><span data-stu-id="69c93-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="69c93-325">är noll om inget steg har angetts eller det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="69c93-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="69c93-326">är längden på den segmenterade matrisen minus en om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="69c93-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="69c93-327">Om slutvärdet för intervallet utelämnas visas värdet för det härledda slut värdet</span><span class="sxs-lookup"><span data-stu-id="69c93-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="69c93-328">är längden på den segmenterade matrisen minus ett om inget steg har angetts eller om det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="69c93-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="69c93-329">är noll om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="69c93-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="69c93-330">Uttryck för mat ris element</span><span class="sxs-lookup"><span data-stu-id="69c93-330">Array Element Expressions</span></span>

<span data-ttu-id="69c93-331">Med ett mat ris uttryck och `Int` ett uttryck kan ett nytt uttryck skapas med operatorn `[` och `]` array element-operatorn.</span><span class="sxs-lookup"><span data-stu-id="69c93-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="69c93-332">Det nya uttrycket är av samma typ som matrisens element typ.</span><span class="sxs-lookup"><span data-stu-id="69c93-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="69c93-333">Om `a` till exempel är kopplat till en matris med `Double`s, `a[4]` är ett `Double` uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="69c93-334">Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.</span><span class="sxs-lookup"><span data-stu-id="69c93-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="69c93-335">Om `a` och `b` är båda matriserna i `Int`s, uttrycks t. ex. ett element från sammanfogningen:</span><span class="sxs-lookup"><span data-stu-id="69c93-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="69c93-336">Alla matriser i Q # är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="69c93-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="69c93-337">Det vill säga det första elementet i en matris `a` är alltid `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="69c93-338">Kopiera och uppdatera uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="69c93-339">Nya matriser kan skapas från befintliga med hjälp av kopierings-och-uppdatera-uttryck.</span><span class="sxs-lookup"><span data-stu-id="69c93-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="69c93-340">Ett kopierings-och-uppdatering-uttryck är ett uttryck för `expression1 w/ expression2 <- expression3`formuläret, `expression1` där måste vara av typen `T[]` av viss typ `T`.</span><span class="sxs-lookup"><span data-stu-id="69c93-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="69c93-341">Den andra `expression2` definierar indexen för de element som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen. `Range`</span><span class="sxs-lookup"><span data-stu-id="69c93-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="69c93-342">Om `expression2` är av typen `Int`måste `expression3` vara av typen `T`.</span><span class="sxs-lookup"><span data-stu-id="69c93-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="69c93-343">Om `expression2` är av typen `Range`måste `expression3` vara av typen `T[]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="69c93-344">Ett Copy-och-Update- `arr w/ idx <- value` uttryck skapar en ny matris med alla element som har angetts till motsvarande- `arr`element i, förutom elementen på `idx`, som är inställda på en/ett i. `value`</span><span class="sxs-lookup"><span data-stu-id="69c93-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="69c93-345">Om `arr` t. ex. innehåller en `[0,1,2,3]`matris,</span><span class="sxs-lookup"><span data-stu-id="69c93-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="69c93-346">`arr w/ 0 <- 10`är matrisen `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="69c93-347">`arr w/ 2 <- 10`är matrisen `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="69c93-348">`arr w/ 0..2..3 <- [10,12]`är matrisen `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="69c93-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="69c93-349">Det finns liknande uttryck för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="69c93-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="69c93-350">Överväg till exempel typen</span><span class="sxs-lookup"><span data-stu-id="69c93-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="69c93-351">Om `c` innehåller `Complex(1.,-1.)`värdet av typen `c w/ Re <- 0.` är det ett uttryck av typen `Complex` som utvärderas till. `Complex(0.,-1.)`</span><span class="sxs-lookup"><span data-stu-id="69c93-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="69c93-352">Villkors uttryck</span><span class="sxs-lookup"><span data-stu-id="69c93-352">Conditional Expressions</span></span>

<span data-ttu-id="69c93-353">Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|`.</span><span class="sxs-lookup"><span data-stu-id="69c93-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="69c93-354">Till exempel `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="69c93-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="69c93-355">I det här exemplet är värdet för villkors uttrycket `c` IF `a==b` sant och `d` om det är falskt.</span><span class="sxs-lookup"><span data-stu-id="69c93-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="69c93-356">De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.</span><span class="sxs-lookup"><span data-stu-id="69c93-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="69c93-357">I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.</span><span class="sxs-lookup"><span data-stu-id="69c93-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="69c93-358">`Op1`Till exempel, `Op2`, och `Op3` alla `Qubit[]=>Unit`, men `Op1` stöder `Adjoint`, `Op2` stöder `Controlled`och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="69c93-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="69c93-359">`flag ? Op1 | Op2`är en `(Qubit[] => Unit)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="69c93-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="69c93-360">`flag ? Op1 | Op3`är en `(Qubit[] => Unit is Adj)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="69c93-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="69c93-361">`flag ? Op2 | Op3`är en `(Qubit[] => Unit is Ctl)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="69c93-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="69c93-362">Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.</span><span class="sxs-lookup"><span data-stu-id="69c93-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="69c93-363">Om är `a==b ? C(qs) | D(qs)`till exempel, om `a==b` är sant, kommer `C` åtgärden att anropas och om den är false anropas bara. `D`</span><span class="sxs-lookup"><span data-stu-id="69c93-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="69c93-364">Detta liknar korta kretsar på andra språk.</span><span class="sxs-lookup"><span data-stu-id="69c93-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="69c93-365">Prioritet för Operator</span><span class="sxs-lookup"><span data-stu-id="69c93-365">Operator Precedence</span></span>

<span data-ttu-id="69c93-366">Alla binära operatorer är rätt associerade, förutom för `^`.</span><span class="sxs-lookup"><span data-stu-id="69c93-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="69c93-367">Hakparenteser `[` och `]`, för mat ris segmentering och indexering, bind före valfri operator.</span><span class="sxs-lookup"><span data-stu-id="69c93-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="69c93-368">Functors `Adjoint` och `Controlled` bind efter mat ris indexering, men före alla andra operatorer.</span><span class="sxs-lookup"><span data-stu-id="69c93-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="69c93-369">Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.</span><span class="sxs-lookup"><span data-stu-id="69c93-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="69c93-370">Operatorer i prioritetsordning, från högsta till lägsta:</span><span class="sxs-lookup"><span data-stu-id="69c93-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="69c93-371">Operator</span><span class="sxs-lookup"><span data-stu-id="69c93-371">Operator</span></span> | <span data-ttu-id="69c93-372">Ariteten</span><span class="sxs-lookup"><span data-stu-id="69c93-372">Arity</span></span> | <span data-ttu-id="69c93-373">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="69c93-373">Description</span></span> | <span data-ttu-id="69c93-374">Operands typer</span><span class="sxs-lookup"><span data-stu-id="69c93-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="69c93-375">avslutande`!`</span><span class="sxs-lookup"><span data-stu-id="69c93-375">trailing `!`</span></span> | <span data-ttu-id="69c93-376">Operator</span><span class="sxs-lookup"><span data-stu-id="69c93-376">Unary</span></span> | <span data-ttu-id="69c93-377">Packa upp</span><span class="sxs-lookup"><span data-stu-id="69c93-377">Unwrap</span></span> | <span data-ttu-id="69c93-378">Valfri användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="69c93-378">Any user-defined type</span></span>
 <span data-ttu-id="69c93-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="69c93-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="69c93-380">Operator</span><span class="sxs-lookup"><span data-stu-id="69c93-380">Unary</span></span> | <span data-ttu-id="69c93-381">Numeriskt negativ, bitvis komplement, logisk negation</span><span class="sxs-lookup"><span data-stu-id="69c93-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="69c93-382">`Int`, `BigInt` eller `Double` för `-`, `Int` eller `BigInt` `~~~`för `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="69c93-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="69c93-383">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-383">Binary</span></span> | <span data-ttu-id="69c93-384">Heltals effekt</span><span class="sxs-lookup"><span data-stu-id="69c93-384">Integer power</span></span> | <span data-ttu-id="69c93-385">`Int`eller `BigInt` för basen `Int` för exponenten</span><span class="sxs-lookup"><span data-stu-id="69c93-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="69c93-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="69c93-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="69c93-387">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-387">Binary</span></span> | <span data-ttu-id="69c93-388">Division, multiplikation, heltals-modulus</span><span class="sxs-lookup"><span data-stu-id="69c93-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="69c93-389">`Int`, `BigInt` eller `Double` för `/` och `*`, `Int` eller `BigInt` för`%`</span><span class="sxs-lookup"><span data-stu-id="69c93-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="69c93-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="69c93-390">`+`, `-`</span></span> | <span data-ttu-id="69c93-391">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-391">Binary</span></span> | <span data-ttu-id="69c93-392">Kombination av addition eller sträng och matris, subtraktion</span><span class="sxs-lookup"><span data-stu-id="69c93-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="69c93-393">`Int``BigInt` eller `Double`, även `String` eller valfri mat ris typ för`+`</span><span class="sxs-lookup"><span data-stu-id="69c93-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="69c93-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="69c93-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="69c93-395">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-395">Binary</span></span> | <span data-ttu-id="69c93-396">Vänster SKIFT, höger Skift</span><span class="sxs-lookup"><span data-stu-id="69c93-396">Left shift, right shift</span></span> | <span data-ttu-id="69c93-397">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="69c93-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="69c93-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="69c93-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="69c93-399">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-399">Binary</span></span> | <span data-ttu-id="69c93-400">Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="69c93-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="69c93-401">`Int``BigInt` eller`Double`</span><span class="sxs-lookup"><span data-stu-id="69c93-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="69c93-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="69c93-402">`==`, `!=`</span></span> | <span data-ttu-id="69c93-403">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-403">Binary</span></span> | <span data-ttu-id="69c93-404">lika med, inte lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="69c93-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="69c93-405">vilken primitiv typ som helst</span><span class="sxs-lookup"><span data-stu-id="69c93-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="69c93-406">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-406">Binary</span></span> | <span data-ttu-id="69c93-407">Bitvis och</span><span class="sxs-lookup"><span data-stu-id="69c93-407">Bitwise AND</span></span> | <span data-ttu-id="69c93-408">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="69c93-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="69c93-409">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-409">Binary</span></span> | <span data-ttu-id="69c93-410">Bitvis XOR</span><span class="sxs-lookup"><span data-stu-id="69c93-410">Bitwise XOR</span></span> | <span data-ttu-id="69c93-411">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="69c93-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="69c93-412">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-412">Binary</span></span> | <span data-ttu-id="69c93-413">Bitvis eller</span><span class="sxs-lookup"><span data-stu-id="69c93-413">Bitwise OR</span></span> | <span data-ttu-id="69c93-414">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="69c93-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="69c93-415">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-415">Binary</span></span> | <span data-ttu-id="69c93-416">Logiska och</span><span class="sxs-lookup"><span data-stu-id="69c93-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="69c93-417">Binär</span><span class="sxs-lookup"><span data-stu-id="69c93-417">Binary</span></span> | <span data-ttu-id="69c93-418">Logiska eller</span><span class="sxs-lookup"><span data-stu-id="69c93-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="69c93-419">Binär/ternär</span><span class="sxs-lookup"><span data-stu-id="69c93-419">Binary/Ternary</span></span> | <span data-ttu-id="69c93-420">Intervall operator</span><span class="sxs-lookup"><span data-stu-id="69c93-420">Range operator</span></span> | `Int`
 <span data-ttu-id="69c93-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="69c93-421">`?` `|`</span></span> | <span data-ttu-id="69c93-422">Ternär</span><span class="sxs-lookup"><span data-stu-id="69c93-422">Ternary</span></span> | <span data-ttu-id="69c93-423">Villkorsstyrd</span><span class="sxs-lookup"><span data-stu-id="69c93-423">Conditional</span></span> | <span data-ttu-id="69c93-424">`Bool`för den vänstra sidan</span><span class="sxs-lookup"><span data-stu-id="69c93-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="69c93-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="69c93-425">`w/` `<-`</span></span> | <span data-ttu-id="69c93-426">Ternär</span><span class="sxs-lookup"><span data-stu-id="69c93-426">Ternary</span></span> | <span data-ttu-id="69c93-427">Kopiera och uppdatera</span><span class="sxs-lookup"><span data-stu-id="69c93-427">Copy-and-update</span></span> | <span data-ttu-id="69c93-428">Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="69c93-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
