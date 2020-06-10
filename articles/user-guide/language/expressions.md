---
title: 'Skriv uttryck i Q #'
description: 'Förstå hur du anger, refererar till och kombinerar konstanter, variabler, operatorer, åtgärder och funktioner som uttryck i Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630001"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="5f87d-103">Skriv uttryck i Q #</span><span class="sxs-lookup"><span data-stu-id="5f87d-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="5f87d-104">Numeriska uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-104">Numeric Expressions</span></span>

<span data-ttu-id="5f87d-105">Numeriska uttryck är uttryck av typen `Int` , `BigInt` eller `Double` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="5f87d-106">Det vill säga att de är antingen heltals-eller flytt ALS nummer.</span><span class="sxs-lookup"><span data-stu-id="5f87d-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="5f87d-107">`Int`litteraler i Q # skrivs enkelt som en följd av siffror.</span><span class="sxs-lookup"><span data-stu-id="5f87d-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="5f87d-108">Hexadecimala och binära heltal stöds med `0x` `0b` prefixet respektive.</span><span class="sxs-lookup"><span data-stu-id="5f87d-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="5f87d-109">`BigInt`litteraler i Q # skrivs med ett efterföljande `l` eller `L` suffix.</span><span class="sxs-lookup"><span data-stu-id="5f87d-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="5f87d-110">Hexadecimala Big heltal stöds med ett "0x"-prefix.</span><span class="sxs-lookup"><span data-stu-id="5f87d-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="5f87d-111">Det innebär att följande är giltig användning av `BigInt` litteraler:</span><span class="sxs-lookup"><span data-stu-id="5f87d-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="5f87d-112">`Double`litteraler i Q # är flytt ALS siffror som skrivs med decimal siffror.</span><span class="sxs-lookup"><span data-stu-id="5f87d-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="5f87d-113">De kan skrivas med ett decimal tecken, `.` och/eller en exponentiell del som anges med "e" eller "e" (efter vilken endast ett möjligt negativt tecken och decimal siffror är giltiga).</span><span class="sxs-lookup"><span data-stu-id="5f87d-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="5f87d-114">Följande är giltiga `Double` litteraler: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="5f87d-115">Med ett mat ris uttryck för valfri element typ `Int` kan ett uttryck skapas med hjälp av den [`Length`](xref:microsoft.quantum.core.length) inbyggda funktionen, med mat ris uttrycket omslutna i parentes `(` och `)` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="5f87d-116">Om till exempel är `a` kopplat till en matris, `Length(a)` är ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="5f87d-117">Om `b` är en matris med heltals matriser, `Int[][]` `Length(b)` är antalet underordnade matriser i `b` och `Length(b[1])` är antalet heltal i den andra under matrisen i `b` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="5f87d-118">Två numeriska uttryck av samma typ, de binära operatorerna `+` , `-` , `*` och `/` kan användas för att skapa ett nytt numeriskt uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="5f87d-119">Typen för det nya uttrycket är detsamma som typerna av komponent uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="5f87d-120">Med två heltals uttryck kan den binära operatorn `^` (Power) användas för att skapa ett nytt heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="5f87d-121">På samma sätt `^` kan användas med två dubbla uttryck för att skapa ett nytt dubbelt uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="5f87d-122">Slutligen `^` kan du använda ett stort heltal till vänster och ett heltal till höger för att skapa ett nytt Big Integer-uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="5f87d-123">I det här fallet måste den andra parametern passa in i 32 bitar. om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="5f87d-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="5f87d-124">Med två heltals-eller Big-heltals uttryck kan ett nytt heltals-eller Big-heltals uttryck skapas med `%` operatörerna (Modulus), `&&&` (bitvis and), `|||` (bitvis or) eller `^^^` (Bitvis XOR).</span><span class="sxs-lookup"><span data-stu-id="5f87d-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="5f87d-125">Med antingen ett heltals-eller Big-heltals uttryck till vänster, och ett heltals uttryck till höger, `<<<` kan operatorerna (aritmetisk vänster Shift) eller `>>>` (aritmetiska höger Shift) användas för att skapa ett nytt uttryck med samma typ som det vänstra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="5f87d-126">Den andra parametern (Shift-värdet) till antingen Shift-operationen måste vara större än eller lika med noll. beteendet för negativa Skift-mängder är odefinierat.</span><span class="sxs-lookup"><span data-stu-id="5f87d-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="5f87d-127">Skift-beloppet för båda Skift-operationen måste också passa i 32 bitar; om inte, kommer ett körnings fel att aktive ras.</span><span class="sxs-lookup"><span data-stu-id="5f87d-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="5f87d-128">Om det tal som ska flyttas är ett heltal tolkas Shift-beloppet, det vill säga `mod 64` en skift på 1 och en förskjutning på 65 har samma resultat.</span><span class="sxs-lookup"><span data-stu-id="5f87d-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="5f87d-129">För både heltals-och Big heltals värden är skiften aritmetiska.</span><span class="sxs-lookup"><span data-stu-id="5f87d-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="5f87d-130">Om du byter ett negativt värde till vänster eller höger resulterar det i ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="5f87d-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="5f87d-131">Det vill säga att flytta ett steg till vänster eller höger är exakt detsamma som att multiplicera eller dividera med 2.</span><span class="sxs-lookup"><span data-stu-id="5f87d-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="5f87d-132">Heltals Division och heltals-Modulus följer samma beteende för negativa tal som C#.</span><span class="sxs-lookup"><span data-stu-id="5f87d-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="5f87d-133">Det vill säga `a % b` har alltid samma signera som och är `a` `b * (a / b) + a % b` alltid lika med `a` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="5f87d-134">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="5f87d-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="5f87d-135">5</span><span class="sxs-lookup"><span data-stu-id="5f87d-135">5</span></span> | <span data-ttu-id="5f87d-136">2</span><span class="sxs-lookup"><span data-stu-id="5f87d-136">2</span></span> | <span data-ttu-id="5f87d-137">2</span><span class="sxs-lookup"><span data-stu-id="5f87d-137">2</span></span> | <span data-ttu-id="5f87d-138">1</span><span class="sxs-lookup"><span data-stu-id="5f87d-138">1</span></span>
 <span data-ttu-id="5f87d-139">5</span><span class="sxs-lookup"><span data-stu-id="5f87d-139">5</span></span> | <span data-ttu-id="5f87d-140">-2</span><span class="sxs-lookup"><span data-stu-id="5f87d-140">-2</span></span> | <span data-ttu-id="5f87d-141">-2</span><span class="sxs-lookup"><span data-stu-id="5f87d-141">-2</span></span> | <span data-ttu-id="5f87d-142">1</span><span class="sxs-lookup"><span data-stu-id="5f87d-142">1</span></span>
 <span data-ttu-id="5f87d-143">-5</span><span class="sxs-lookup"><span data-stu-id="5f87d-143">-5</span></span> | <span data-ttu-id="5f87d-144">2</span><span class="sxs-lookup"><span data-stu-id="5f87d-144">2</span></span> | <span data-ttu-id="5f87d-145">-2</span><span class="sxs-lookup"><span data-stu-id="5f87d-145">-2</span></span> | <span data-ttu-id="5f87d-146">-1</span><span class="sxs-lookup"><span data-stu-id="5f87d-146">-1</span></span>
 <span data-ttu-id="5f87d-147">-5</span><span class="sxs-lookup"><span data-stu-id="5f87d-147">-5</span></span> | <span data-ttu-id="5f87d-148">-2</span><span class="sxs-lookup"><span data-stu-id="5f87d-148">-2</span></span> | <span data-ttu-id="5f87d-149">2</span><span class="sxs-lookup"><span data-stu-id="5f87d-149">2</span></span> | <span data-ttu-id="5f87d-150">-1</span><span class="sxs-lookup"><span data-stu-id="5f87d-150">-1</span></span>

<span data-ttu-id="5f87d-151">Big Integer-Division och Modulus fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="5f87d-152">Ett nytt uttryck kan skapas med hjälp av ett numeriskt uttryck med hjälp av den `-` unära operatorn.</span><span class="sxs-lookup"><span data-stu-id="5f87d-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="5f87d-153">Det nya uttrycket är av samma typ som komponent uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="5f87d-154">Med alla heltals-eller Big-heltals uttryck kan ett nytt uttryck av samma typ skapas med den `~~~` unära operatorn (bitvis komplement).</span><span class="sxs-lookup"><span data-stu-id="5f87d-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="5f87d-155">Booleska uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-155">Boolean Expressions</span></span>

<span data-ttu-id="5f87d-156">De två `Bool` literala värdena är `true` och `false` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="5f87d-157">Om du har två uttryck av samma primitiva typ `==` kan de och `!=` binära operatorerna användas för att skapa ett `Bool` uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="5f87d-158">Uttrycket är sant om de två uttrycken är lika och falskt om inte.</span><span class="sxs-lookup"><span data-stu-id="5f87d-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="5f87d-159">Värden för användardefinierade typer kan inte jämföras, men endast de värden som inte är figursatta kan jämföras.</span><span class="sxs-lookup"><span data-stu-id="5f87d-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="5f87d-160">Du kan till exempel använda operatorn "unwrap" `!` (förklaras i detalj på [typer i Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)).</span><span class="sxs-lookup"><span data-stu-id="5f87d-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="5f87d-161">Likhets jämförelse för `Qubit` värden är identitets likhet, det vill säga om de två uttrycken identifierar samma qubit.</span><span class="sxs-lookup"><span data-stu-id="5f87d-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="5f87d-162">Status för de två qubits jämförs inte, används, mäts eller ändras av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="5f87d-163">Jämförelse av `Double` värden kan vara missvisande på grund av avrundnings effekter.</span><span class="sxs-lookup"><span data-stu-id="5f87d-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="5f87d-164">Till exempel `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="5f87d-165">Två numeriska uttryck, de binära operatorerna,, `>` `<` `>=` och `<=` kan användas för att skapa ett nytt booleskt uttryck som är sant om det första uttrycket är större än, mindre än, större än eller lika med eller mindre än eller lika med det andra uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="5f87d-166">Med två booleska uttryck `and` kan de och `or` binära operatorerna användas för att skapa ett nytt booleskt uttryck som är sant om båda uttrycken (ansvars båda eller båda) är sanna.</span><span class="sxs-lookup"><span data-stu-id="5f87d-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="5f87d-167">Med alla booleska uttryck kan den `not` unära operatorn användas för att skapa ett nytt booleskt uttryck som är sant om komponent uttrycket är falskt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="5f87d-168">Sträng uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-168">String Expressions</span></span>

<span data-ttu-id="5f87d-169">Q # tillåter att strängar används i `fail` instruktionen (förklaras i [kontroll flödet](xref:microsoft.quantum.guide.controlflow#fail-statement)) och i [`Message`](xref:microsoft.quantum.intrinsic.message) funktionen standard.</span><span class="sxs-lookup"><span data-stu-id="5f87d-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="5f87d-170">Det speciella beteendet för den senare beror på vilken simulator som används, men skriver vanligt vis ett meddelande till värd konsolen när den anropas under ett Q #-program.</span><span class="sxs-lookup"><span data-stu-id="5f87d-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="5f87d-171">Strängar i Q # är antingen litteraler eller interpolerade strängar.</span><span class="sxs-lookup"><span data-stu-id="5f87d-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="5f87d-172">Sträng litteraler liknar enkla sträng litteraler på de flesta språk: en sekvens med Unicode-tecken som omges av dubbla citat tecken `"` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="5f87d-173">I en sträng kan back snedstrecket `\` användas för att undvika ett dubbelt citat tecken och för att infoga en ny rad som `\n` , en vagn retur som `\r` och en flik som `\t` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="5f87d-174">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="5f87d-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="5f87d-175">Interpolerade strängar</span><span class="sxs-lookup"><span data-stu-id="5f87d-175">Interpolated strings</span></span>

<span data-ttu-id="5f87d-176">Q #-syntaxen för String-interpolation är en delmängd av C#-syntaxen, men vi sammanfattar här viktiga punkter som de gäller för Q #.</span><span class="sxs-lookup"><span data-stu-id="5f87d-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="5f87d-177">De huvudsakliga distinkta beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="5f87d-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="5f87d-178">För att identifiera en tecken sträng som en interpolerad sträng, lägga den med `$` symbolen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="5f87d-179">Det går inte att ha blank steg mellan `$` och `"` som startar en tecken sträng.</span><span class="sxs-lookup"><span data-stu-id="5f87d-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="5f87d-180">Följande är ett grundläggande exempel [`Message`](xref:microsoft.quantum.intrinsic.message) som använder funktionen för att skriva resultatet av en mätning till-konsolen, tillsammans med andra Q #-uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="5f87d-181">Alla giltiga Q #-uttryck kan visas i en interpolerad sträng.</span><span class="sxs-lookup"><span data-stu-id="5f87d-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="5f87d-182">Du hittar mer information om C#-syntaxen i [*interpolerade strängar*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="5f87d-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="5f87d-183">Den mest viktiga skillnaden är att Q # inte stöder orda Grant-interpolerade strängar (multi-line).</span><span class="sxs-lookup"><span data-stu-id="5f87d-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="5f87d-184">Uttryck i en interpolerad sträng följer Q # syntax, inte C#-syntax.</span><span class="sxs-lookup"><span data-stu-id="5f87d-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="5f87d-185">Intervall uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-185">Range Expressions</span></span>

<span data-ttu-id="5f87d-186">Alla tre `Int` uttryck `start` , `step` , och `stop` , `start .. step .. stop` är ett intervall uttryck vars första element är, det `start` andra elementet är `start+step` , det tredje elementet, `start+step+step` osv., tills `stop` det skickas.</span><span class="sxs-lookup"><span data-stu-id="5f87d-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="5f87d-187">Ett intervall kan vara tomt om, t. ex. `step` är positivt och `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="5f87d-188">Det sista elementet i intervallet är `stop` om skillnaden mellan `start` och `stop` är en integral multipel av, det vill säga `step` intervallet i båda ändar.</span><span class="sxs-lookup"><span data-stu-id="5f87d-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="5f87d-189">Två uttryck har `Int` angetts `start` och `stop` `start .. stop` är ett intervall uttryck som är lika med `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="5f87d-190">Observera att det underförstådda `step` är + 1 även om `stop` är mindre än `start` . i så fall är intervallet tomt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="5f87d-191">Några exempel intervall är:</span><span class="sxs-lookup"><span data-stu-id="5f87d-191">Some example ranges are:</span></span>

- <span data-ttu-id="5f87d-192">`1..3`är intervallet 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="5f87d-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="5f87d-193">`2..2..5`är intervallet 2, 4.</span><span class="sxs-lookup"><span data-stu-id="5f87d-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="5f87d-194">`2..2..6`är intervallet 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="5f87d-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="5f87d-195">`6..-2..2`är intervallet 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="5f87d-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="5f87d-196">`2..1`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="5f87d-197">`2..6..7`är intervallet 2.</span><span class="sxs-lookup"><span data-stu-id="5f87d-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="5f87d-198">`2..2..1`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="5f87d-199">`1..-1..2`är det tomma intervallet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="5f87d-200">Qubit-uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-200">Qubit Expressions</span></span>

<span data-ttu-id="5f87d-201">De enda `Qubit` uttrycken är symboler som är kopplade till `Qubit` värden eller mat ris element `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="5f87d-202">Det finns inga `Qubit` litteraler.</span><span class="sxs-lookup"><span data-stu-id="5f87d-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="5f87d-203">Pauli-uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-203">Pauli Expressions</span></span>

<span data-ttu-id="5f87d-204">De fyra `Pauli` värdena, `PauliI` , `PauliX` , `PauliY` och `PauliZ` , är giltiga `Pauli` uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="5f87d-205">Förutom så är de enda `Pauli` uttrycken symboler som är kopplade till `Pauli` värden eller mat ris element `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="5f87d-206">Resultat uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-206">Result Expressions</span></span>

<span data-ttu-id="5f87d-207">De två `Result` värdena `One` och `Zero` , är giltiga `Result` uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="5f87d-208">Förutom så är de enda `Result` uttrycken symboler som är kopplade till `Result` värden eller mat ris element `Result` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="5f87d-209">Observera särskilt att `One` inte är detsamma som heltalet `1` och det finns ingen direkt konvertering mellan dem.</span><span class="sxs-lookup"><span data-stu-id="5f87d-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="5f87d-210">Samma sak gäller `Zero` och `0` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="5f87d-211">Tuple-uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-211">Tuple Expressions</span></span>

<span data-ttu-id="5f87d-212">En tupel litteral är en sekvens med element uttryck av lämplig typ, avgränsade med kommatecken, som omges av `(` och `)` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="5f87d-213">Är till exempel `(1, One)` ett `(Int, Result)` uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="5f87d-214">Förutom litteraler är de enda tuple-uttrycken symboler som är kopplade till tuple-värden, mat ris element i tuple-matriser och anrops bara anrop som returnerar tupler.</span><span class="sxs-lookup"><span data-stu-id="5f87d-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="5f87d-215">Användardefinierade typ uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="5f87d-216">En litteral av en användardefinierad typ består av typ namnet följt av en tupel av typens bastyp.</span><span class="sxs-lookup"><span data-stu-id="5f87d-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="5f87d-217">Om är till exempel `IntPair` en användardefinierad typ som baseras på, är `(Int, Int)` `IntPair(2, 3)` en giltig litteral av den typen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="5f87d-218">Förutom litteraler är de enda uttrycken av en användardefinierad typ symboler som är kopplade till värden av den typen, mat ris element för matriser av den typen och anrops bara anrop som returnerar den typen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="5f87d-219">Packa upp uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-219">Unwrap Expressions</span></span>

<span data-ttu-id="5f87d-220">I Q # är unwrap-operatorn ett avslutande utrops tecken `!` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="5f87d-221">Om är till exempel `IntPair` en användardefinierad typ med underliggande typ `(Int, Int)` och `s` var en variabel med värde `IntPair(2, 3)` , `s!` skulle det vara `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="5f87d-222">För användardefinierade typer som definieras i termer av andra användardefinierade typer, kan den avbrytande operatorn upprepas. `s!!`anger t. ex. dubblerat-värde för `s` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="5f87d-223">Om `WrappedPair` är en användardefinierad typ med underliggande typ `IntPair` och `t` är en variabel med värde `WrappedPair(IntPair(1,2))` , blir `t!!` det alltså `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="5f87d-224">`!`Operatören har högre prioritet än andra andra operatorer än `[]` för mat ris indexering och segmentering.</span><span class="sxs-lookup"><span data-stu-id="5f87d-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="5f87d-225">`!`och `[]` BIND positions läge, som är, `a[i]![3]` ska läsas som `((a[i])!)[3]` : ta det `i` "th"-elementet i `a` , packa upp det och hämta det tredje elementet i det icke-omslutna värdet (som måste vara en matris).</span><span class="sxs-lookup"><span data-stu-id="5f87d-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="5f87d-226">Prioriteten hos `!` operatorn har en effekt som kanske inte är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="5f87d-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="5f87d-227">Om en funktion eller åtgärd returnerar ett värde som sedan blir omsluten, måste funktionen eller åtgärds anropet omges av parenteser, så att argumentet tupel binder till anropet i stället för att avbrytas.</span><span class="sxs-lookup"><span data-stu-id="5f87d-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="5f87d-228">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="5f87d-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="5f87d-229">Mat ris uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-229">Array Expressions</span></span>

<span data-ttu-id="5f87d-230">En mat ris sträng är en sekvens av ett eller flera element uttryck, avgränsade med kommatecken, som omges av `[` och `]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="5f87d-231">Alla element måste vara kompatibla med samma typ.</span><span class="sxs-lookup"><span data-stu-id="5f87d-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="5f87d-232">Med två matriser av samma typ kan den binära `+` operatorn användas för att skapa en ny matris som är sammanfogningen av de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="5f87d-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="5f87d-233">Till exempel `[1,2,3] + [4,5,6]` är `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="5f87d-234">Skapa matris</span><span class="sxs-lookup"><span data-stu-id="5f87d-234">Array Creation</span></span>

<span data-ttu-id="5f87d-235">Med en typ och ett `Int` uttryck `new` kan operatorn användas för att allokera en ny matris med den aktuella storleken.</span><span class="sxs-lookup"><span data-stu-id="5f87d-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="5f87d-236">Allokera till exempel `new Int[i + 1]` en ny `Int` matris med `i + 1` element.</span><span class="sxs-lookup"><span data-stu-id="5f87d-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="5f87d-237">Tomma mat ris strängar, `[]` tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="5f87d-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="5f87d-238">I stället använda `new ★[0]` , där `★` är plats hållare för lämplig typ, kan du skapa den önskade matrisen med längden noll.</span><span class="sxs-lookup"><span data-stu-id="5f87d-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="5f87d-239">Elementen i en ny matris initieras till ett typ beroende standardvärde.</span><span class="sxs-lookup"><span data-stu-id="5f87d-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="5f87d-240">I de flesta fall är detta en variation på noll.</span><span class="sxs-lookup"><span data-stu-id="5f87d-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="5f87d-241">Det finns inget rimligt standardvärde för qubits och callables, som är referenser till entiteter.</span><span class="sxs-lookup"><span data-stu-id="5f87d-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="5f87d-242">Därför är standardvärdet en ogiltig referens som inte kan användas utan att orsaka körnings fel för dessa typer.</span><span class="sxs-lookup"><span data-stu-id="5f87d-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="5f87d-243">Detta liknar en null-referens i språk som C# eller Java.</span><span class="sxs-lookup"><span data-stu-id="5f87d-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="5f87d-244">Matriser som innehåller qubits eller callables måste initieras korrekt med icke-standardvärden innan deras element kan användas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="5f87d-245">Du hittar lämpliga initierings rutiner i <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="5f87d-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="5f87d-246">Standardvärdena för varje typ är:</span><span class="sxs-lookup"><span data-stu-id="5f87d-246">The default values for each type are:</span></span>

<span data-ttu-id="5f87d-247">Typ</span><span class="sxs-lookup"><span data-stu-id="5f87d-247">Type</span></span> | <span data-ttu-id="5f87d-248">Standard</span><span class="sxs-lookup"><span data-stu-id="5f87d-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="5f87d-249">_Ogiltig qubit_</span><span class="sxs-lookup"><span data-stu-id="5f87d-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="5f87d-250">Det tomma intervallet,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="5f87d-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="5f87d-251">_Ogiltigt anrops bara_</span><span class="sxs-lookup"><span data-stu-id="5f87d-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="5f87d-252">Tuple-typer är initierade element-by-element.</span><span class="sxs-lookup"><span data-stu-id="5f87d-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="5f87d-253">Mat ris element</span><span class="sxs-lookup"><span data-stu-id="5f87d-253">Array Elements</span></span>

<span data-ttu-id="5f87d-254">Med ett mat ris uttryck och ett `Int` uttryck kan ett nytt uttryck skapas med `[` `]` operatorn och array element-operatorn.</span><span class="sxs-lookup"><span data-stu-id="5f87d-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="5f87d-255">Det nya uttrycket är av samma typ som matrisens element typ.</span><span class="sxs-lookup"><span data-stu-id="5f87d-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="5f87d-256">Om till exempel är `a` kopplat till en matris med `Double` s, `a[4]` är ett `Double` uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="5f87d-257">Om mat ris uttrycket inte är en enkel identifierare måste det omges av parenteser för att välja ett element.</span><span class="sxs-lookup"><span data-stu-id="5f87d-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="5f87d-258">Om `a` och `b` är båda matriserna i `Int` s, uttrycks t. ex. ett element från sammanfogningen:</span><span class="sxs-lookup"><span data-stu-id="5f87d-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="5f87d-259">Alla matriser i Q # är noll-baserade.</span><span class="sxs-lookup"><span data-stu-id="5f87d-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="5f87d-260">Det vill säga det första elementet i en matris `a` är alltid `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="5f87d-261">Mat ris segment</span><span class="sxs-lookup"><span data-stu-id="5f87d-261">Array Slices</span></span>

<span data-ttu-id="5f87d-262">Med ett mat ris uttryck och ett `Range` uttryck kan ett nytt uttryck skapas med `[` `]` operatorn array och array.</span><span class="sxs-lookup"><span data-stu-id="5f87d-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="5f87d-263">Det nya uttrycket är av samma typ som matrisen och kommer att innehålla de mat ris objekt som indexeras av elementen i `Range` , i den ordning som definieras av `Range` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="5f87d-264">Om till exempel är `a` kopplat till en matris med `Double` s, `a[3..-1..0]` är ett `Double[]` uttryck som innehåller de första fyra elementen i, `a` men i omvänd ordning som de visas i `a` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="5f87d-265">Om `Range` är tom, kommer den resulterande matrisen att ha längden noll.</span><span class="sxs-lookup"><span data-stu-id="5f87d-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="5f87d-266">Precis som med referenser till mat ris element, om mat ris uttrycket inte är en enkel identifierare, måste det omges av parenteser för att kunna segmentera.</span><span class="sxs-lookup"><span data-stu-id="5f87d-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="5f87d-267">Om `a` och `b` är båda matriserna i `Int` s, uttrycks en sektor från sammanfogningen som:</span><span class="sxs-lookup"><span data-stu-id="5f87d-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="5f87d-268">Uppskjutna start-/slut värden</span><span class="sxs-lookup"><span data-stu-id="5f87d-268">Inferred start/end values</span></span>

<span data-ttu-id="5f87d-269">Från och med vår 0,8-utgåva stöder vi sammanhangsbaserade uttryck för intervall segmentering.</span><span class="sxs-lookup"><span data-stu-id="5f87d-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="5f87d-270">I synnerhet kan intervall start-och slut värden utelämnas i kontexten för ett intervall segment uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="5f87d-271">I så fall kommer kompileraren att tillämpa följande regler för att härleda de avsedda avgränsarna för intervallet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="5f87d-272">Om start värde för intervall t. ex. utelämnas används värdet för uppskjutet start värde</span><span class="sxs-lookup"><span data-stu-id="5f87d-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="5f87d-273">är noll om inget steg har angetts eller det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="5f87d-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5f87d-274">är längden på den segmenterade matrisen minus en om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="5f87d-275">Om slutvärdet för intervallet utelämnas visas värdet för det härledda slut värdet</span><span class="sxs-lookup"><span data-stu-id="5f87d-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="5f87d-276">är längden på den segmenterade matrisen minus ett om inget steg har angetts eller om det angivna steget är positivt och</span><span class="sxs-lookup"><span data-stu-id="5f87d-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5f87d-277">är noll om det angivna steget är negativt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="5f87d-278">Kopiera och uppdatera uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="5f87d-279">Eftersom alla Q #-typer är värde typer, där qubits tar en lite speciell roll, skapas en "kopia" när ett värde är kopplat till en symbol eller när en symbol har bundits.</span><span class="sxs-lookup"><span data-stu-id="5f87d-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="5f87d-280">Detta är att säga att Q # är detsamma som om en kopia skapades för tilldelningen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="5f87d-281">Naturligtvis i praktiken är det bara de relevanta delarna som faktiskt återskapas vid behov.</span><span class="sxs-lookup"><span data-stu-id="5f87d-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="5f87d-282">Detta omfattar även matriser.</span><span class="sxs-lookup"><span data-stu-id="5f87d-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="5f87d-283">I synnerhet är det inte möjligt att uppdatera mat ris objekt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="5f87d-284">Om du vill ändra en befintlig matris måste du använda en *kopierings-och-uppdaterings* funktion.</span><span class="sxs-lookup"><span data-stu-id="5f87d-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="5f87d-285">Nya matriser kan skapas från befintliga med hjälp av *kopierings-och-uppdatera-* uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="5f87d-286">Ett kopierings-och-uppdatering-uttryck är ett uttryck för formuläret `expression1 w/ expression2 <- expression3` , där `expression1` måste vara av typen av `T[]` viss typ `T` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="5f87d-287">Den andra `expression2` definierar indexen för de element som ska ändras jämfört med matrisen i `expression1` och måste vara av typen `Int` eller av typen `Range` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="5f87d-288">Om `expression2` är av typen `Int` måste `expression3` vara av typen `T` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="5f87d-289">Om `expression2` är av typen `Range` måste `expression3` vara av typen `T[]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="5f87d-290">Ett Copy-och-Update-uttryck `arr w/ idx <- value` skapar en ny matris med alla element som har angetts till motsvarande-element i `arr` , förutom elementen på `idx` , som är inställda på en/ett i `value` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="5f87d-291">Om t. ex. `arr` innehåller en matris `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="5f87d-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="5f87d-292">`arr w/ 0 <- 10`är matrisen `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="5f87d-293">`arr w/ 2 <- 10`är matrisen `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="5f87d-294">`arr w/ 0..2..3 <- [10,12]`är matrisen `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="5f87d-295">Kopiera och uppdatera uttryck för namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="5f87d-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="5f87d-296">Det finns liknande uttryck för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="5f87d-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="5f87d-297">Överväg till exempel typen</span><span class="sxs-lookup"><span data-stu-id="5f87d-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="5f87d-298">Om `c` innehåller värdet av typen `Complex(1., -1.)` `c w/ Re <- 0.` är det ett uttryck av typen `Complex` som utvärderas till `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="5f87d-299">Ojämna matriser</span><span class="sxs-lookup"><span data-stu-id="5f87d-299">Jagged Arrays</span></span>

<span data-ttu-id="5f87d-300">En taggad matris, som ibland kallas matriser, är en matris vars element är matriser.</span><span class="sxs-lookup"><span data-stu-id="5f87d-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="5f87d-301">Elementen i en taggad matris kan ha olika storlekar.</span><span class="sxs-lookup"><span data-stu-id="5f87d-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="5f87d-302">I följande exempel visas hur du deklarerar och initierar en taggad matris som representerar en multiplikations tabell.</span><span class="sxs-lookup"><span data-stu-id="5f87d-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="5f87d-303">Matriser med callables</span><span class="sxs-lookup"><span data-stu-id="5f87d-303">Arrays of callables</span></span> 

<span data-ttu-id="5f87d-304">Observera att det finns mer information om typer som kan anropas nedan, samt på nästa sida, [åtgärder och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="5f87d-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="5f87d-305">Om den gemensamma element typen är en åtgärds-eller funktions typ måste alla element ha samma indata och utdata.</span><span class="sxs-lookup"><span data-stu-id="5f87d-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="5f87d-306">Element typen för matrisen kommer att ha stöd för alla functors som stöds av alla element.</span><span class="sxs-lookup"><span data-stu-id="5f87d-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="5f87d-307">Till exempel, `Op1` `Op2` , och `Op3` alla `Qubit[] => Unit` , men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="5f87d-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5f87d-308">`[Op1, Op2]`är en matris med `(Qubit[] => Unit)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5f87d-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="5f87d-309">`[Op1, Op3]`är en matris med `(Qubit[] => Unit is Adj)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5f87d-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="5f87d-310">`[Op2, Op3]`är en matris med `(Qubit[] => Unit is Ctl)` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5f87d-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="5f87d-311">Men medan `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` -åtgärder har den vanligaste bastypen för `(Qubit[] => Unit)` , Observera att matriser *för* dessa operatörer inte delar en gemensam bastyp.</span><span class="sxs-lookup"><span data-stu-id="5f87d-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="5f87d-312">Skulle till exempel `[[Op1], [Op2]]` kunna generera ett fel eftersom det försöker skapa en matris av de inkompatibla mat ris typerna `(Qubit[] => Unit is Adj)[]` och `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="5f87d-313">Villkors uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-313">Conditional Expressions</span></span>

<span data-ttu-id="5f87d-314">Med två andra uttryck av samma typ och ett booleskt uttryck, kan villkors uttrycket skapas med hjälp av frågetecknet `?` och det lodräta fältet `|` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="5f87d-315">Till exempel `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="5f87d-316">I det här exemplet är värdet för villkors uttrycket `c` IF `a==b` sant och `d` om det är falskt.</span><span class="sxs-lookup"><span data-stu-id="5f87d-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="5f87d-317">Villkors uttryck med callables</span><span class="sxs-lookup"><span data-stu-id="5f87d-317">Conditional expressions with callables</span></span>

<span data-ttu-id="5f87d-318">De två uttrycken kan utvärderas för åtgärder som har samma indata och utdata, men som stöder olika functors.</span><span class="sxs-lookup"><span data-stu-id="5f87d-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="5f87d-319">I det här fallet är typen av villkors uttryck en åtgärd med de indata och utdata som stöder alla functors som stöds av båda uttrycken.</span><span class="sxs-lookup"><span data-stu-id="5f87d-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="5f87d-320">Till exempel, `Op1` `Op2` , och `Op3` alla `Qubit[]=>Unit` , men `Op1` stöder `Adjoint` , `Op2` stöder `Controlled` och `Op3` stöder båda:</span><span class="sxs-lookup"><span data-stu-id="5f87d-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5f87d-321">`flag ? Op1 | Op2`är en `(Qubit[] => Unit)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5f87d-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="5f87d-322">`flag ? Op1 | Op3`är en `(Qubit[] => Unit is Adj)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5f87d-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="5f87d-323">`flag ? Op2 | Op3`är en `(Qubit[] => Unit is Ctl)` åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5f87d-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="5f87d-324">Om något av de två möjliga resultat uttrycken innehåller en funktion eller ett åtgärds anrop görs det anropet endast om det är det värde som ska vara värdet för anropet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="5f87d-325">Om är till exempel, `a==b ? C(qs) | D(qs)` om `a==b` är sant `C` , kommer åtgärden att anropas och om den är false `D` anropas bara.</span><span class="sxs-lookup"><span data-stu-id="5f87d-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="5f87d-326">Detta liknar korta kretsar på andra språk.</span><span class="sxs-lookup"><span data-stu-id="5f87d-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="5f87d-327">Anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-327">Callable Expressions</span></span>

<span data-ttu-id="5f87d-328">En anrops bara literal är namnet på en åtgärd eller funktion som definierats i kompilerings omfånget.</span><span class="sxs-lookup"><span data-stu-id="5f87d-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="5f87d-329">Är till exempel `X` en åtgärds-literal som refererar till standard biblioteks `X` åtgärden och `Message` är en funktions sträng som refererar till standard biblioteks `Message` funktionen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="5f87d-330">Om en åtgärd har stöd för `Adjoint` Functor `Adjoint op` är ett åtgärds uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f87d-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="5f87d-331">På samma sätt `Controlled` `Controlled op` är det ett åtgärds uttryck om åtgärden stöder Functor.</span><span class="sxs-lookup"><span data-stu-id="5f87d-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="5f87d-332">Typerna av de här uttrycken anges i specialisering för att [anropa en åtgärd](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="5f87d-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="5f87d-333">Functors ( `Adjoint` och `Controlled` ) binder mer nära varandra än alla andra operatorer, förutom unwrap-operatorn `!` och mat ris indexering med [] ".</span><span class="sxs-lookup"><span data-stu-id="5f87d-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="5f87d-334">Därför är följande alla juridiska, förutsatt att de åtgärder som har stöd för de functors som används:</span><span class="sxs-lookup"><span data-stu-id="5f87d-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="5f87d-335">Typ-parametriserade anrops bara uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="5f87d-336">En anrops bara literal kan användas som ett värde, t. ex. tilldela en variabel eller skicka till ett annat anrop.</span><span class="sxs-lookup"><span data-stu-id="5f87d-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="5f87d-337">I det här fallet, om anropet har [typ parametrar](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), måste de anges som en del av det anropade värdet.</span><span class="sxs-lookup"><span data-stu-id="5f87d-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="5f87d-338">Ett anrops bara värde kan inte ha ospecificerade typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="5f87d-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="5f87d-339">Om är till exempel `Fun` en funktion med signatur `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="5f87d-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="5f87d-340">Anrops anrops anrops uttryck</span><span class="sxs-lookup"><span data-stu-id="5f87d-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="5f87d-341">Ett anrops bara uttryck (operation eller Function) och ett tuple-uttryck av indatatypen för den anropande signaturen kan vara ett anrops uttryck genom att lägga till tuple-uttrycket i det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="5f87d-342">Typen av anrops uttryck är utdatatypen för den anropande signaturen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="5f87d-343">Om är till exempel en `Op` åtgärd med signatur `((Int, Qubit) => Double)` , `Op(3, qubit1)` är ett uttryck av typen `Double` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5f87d-344">På samma sätt, om `Sin` är en funktion med signatur `(Double -> Double)` , `Sin(0.1)` är ett uttryck av typen `Double` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5f87d-345">Slutligen, om `Builder` är en funktion med signatur `(Int -> (Int -> Int))` , `Builder(3)` är en funktion från till int.</span><span class="sxs-lookup"><span data-stu-id="5f87d-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="5f87d-346">Om resultatet av ett anrops bara uttryck anropas krävs ett extra paren tes tecken runt det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="5f87d-347">För att anropa resultatet av anrop `Builder` från föregående stycke är därför rätt syntax:</span><span class="sxs-lookup"><span data-stu-id="5f87d-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="5f87d-348">När du anropar en [typ-parameter](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) som kan anropas kan de faktiska typ parametrarna anges inom vinkelparenteser `<` och `>` efter det anrops bara uttrycket.</span><span class="sxs-lookup"><span data-stu-id="5f87d-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="5f87d-349">Detta är vanligt vis onödigt eftersom Q #-kompilatorn kommer att härleda de faktiska typerna.</span><span class="sxs-lookup"><span data-stu-id="5f87d-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="5f87d-350">*Det krävs* dock för [partiella program](xref:microsoft.quantum.guide.operationsfunctions#partial-application) om ett argument av typen parameter lämnas ospecificerade.</span><span class="sxs-lookup"><span data-stu-id="5f87d-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="5f87d-351">Det är också användbart att skicka åtgärder med olika Functor-funktioner som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="5f87d-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="5f87d-352">Om har exempelvis signatur och har signatur, `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` och `Op3` har signatur `(Qubit[] => Unit)` , för att anropa `Func` med `Op1` som första argument, `Op2` som den andra, och `Op3` som tredje:</span><span class="sxs-lookup"><span data-stu-id="5f87d-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="5f87d-353">Typ specifikationen krävs eftersom `Op3` och `Op1` har olika typer, så att kompileraren behandlar detta som tvetydigt utan specifikationen.</span><span class="sxs-lookup"><span data-stu-id="5f87d-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="5f87d-354">Prioritet för Operator</span><span class="sxs-lookup"><span data-stu-id="5f87d-354">Operator Precedence</span></span>

<span data-ttu-id="5f87d-355">Alla binära operatorer är rätt associerade, förutom för `^` .</span><span class="sxs-lookup"><span data-stu-id="5f87d-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="5f87d-356">Hakparenteser `[` och `]` , för mat ris segmentering och indexering, bind före valfri operator.</span><span class="sxs-lookup"><span data-stu-id="5f87d-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="5f87d-357">Functors `Adjoint` och `Controlled` BIND efter mat ris indexering, men före alla andra operatorer.</span><span class="sxs-lookup"><span data-stu-id="5f87d-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="5f87d-358">Parenteser för åtgärds-och funktions anrop binder också före en operator, men efter mat ris indexering och functors.</span><span class="sxs-lookup"><span data-stu-id="5f87d-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="5f87d-359">Operatorer i prioritetsordning, från högsta till lägsta:</span><span class="sxs-lookup"><span data-stu-id="5f87d-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="5f87d-360">Operator</span><span class="sxs-lookup"><span data-stu-id="5f87d-360">Operator</span></span> | <span data-ttu-id="5f87d-361">Ariteten</span><span class="sxs-lookup"><span data-stu-id="5f87d-361">Arity</span></span> | <span data-ttu-id="5f87d-362">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5f87d-362">Description</span></span> | <span data-ttu-id="5f87d-363">Operands typer</span><span class="sxs-lookup"><span data-stu-id="5f87d-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="5f87d-364">avslutande`!`</span><span class="sxs-lookup"><span data-stu-id="5f87d-364">trailing `!`</span></span> | <span data-ttu-id="5f87d-365">Enställig</span><span class="sxs-lookup"><span data-stu-id="5f87d-365">Unary</span></span> | <span data-ttu-id="5f87d-366">Packa upp</span><span class="sxs-lookup"><span data-stu-id="5f87d-366">Unwrap</span></span> | <span data-ttu-id="5f87d-367">Valfri användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="5f87d-367">Any user-defined type</span></span>
 <span data-ttu-id="5f87d-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="5f87d-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="5f87d-369">Enställig</span><span class="sxs-lookup"><span data-stu-id="5f87d-369">Unary</span></span> | <span data-ttu-id="5f87d-370">Numeriskt negativ, bitvis komplement, logisk negation</span><span class="sxs-lookup"><span data-stu-id="5f87d-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="5f87d-371">`Int`, `BigInt` eller `Double` för `-` , `Int` eller `BigInt` `~~~` för `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="5f87d-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="5f87d-372">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-372">Binary</span></span> | <span data-ttu-id="5f87d-373">Heltals effekt</span><span class="sxs-lookup"><span data-stu-id="5f87d-373">Integer power</span></span> | <span data-ttu-id="5f87d-374">`Int`eller `BigInt` för basen `Int` för exponenten</span><span class="sxs-lookup"><span data-stu-id="5f87d-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="5f87d-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="5f87d-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="5f87d-376">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-376">Binary</span></span> | <span data-ttu-id="5f87d-377">Division, multiplikation, heltals-modulus</span><span class="sxs-lookup"><span data-stu-id="5f87d-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="5f87d-378">`Int`, `BigInt` eller `Double` för `/` och `*` , `Int` eller `BigInt` för`%`</span><span class="sxs-lookup"><span data-stu-id="5f87d-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="5f87d-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="5f87d-379">`+`, `-`</span></span> | <span data-ttu-id="5f87d-380">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-380">Binary</span></span> | <span data-ttu-id="5f87d-381">Kombination av addition eller sträng och matris, subtraktion</span><span class="sxs-lookup"><span data-stu-id="5f87d-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="5f87d-382">`Int``BigInt`eller `Double` , även `String` eller valfri mat ris typ för`+`</span><span class="sxs-lookup"><span data-stu-id="5f87d-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="5f87d-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="5f87d-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="5f87d-384">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-384">Binary</span></span> | <span data-ttu-id="5f87d-385">Vänster SKIFT, höger Skift</span><span class="sxs-lookup"><span data-stu-id="5f87d-385">Left shift, right shift</span></span> | <span data-ttu-id="5f87d-386">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5f87d-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="5f87d-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="5f87d-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="5f87d-388">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-388">Binary</span></span> | <span data-ttu-id="5f87d-389">Mindre än, mindre än eller lika med, större än, större än eller-lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="5f87d-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="5f87d-390">`Int``BigInt`eller`Double`</span><span class="sxs-lookup"><span data-stu-id="5f87d-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="5f87d-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="5f87d-391">`==`, `!=`</span></span> | <span data-ttu-id="5f87d-392">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-392">Binary</span></span> | <span data-ttu-id="5f87d-393">lika med, inte lika med jämförelser</span><span class="sxs-lookup"><span data-stu-id="5f87d-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="5f87d-394">vilken primitiv typ som helst</span><span class="sxs-lookup"><span data-stu-id="5f87d-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="5f87d-395">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-395">Binary</span></span> | <span data-ttu-id="5f87d-396">Bitvis och</span><span class="sxs-lookup"><span data-stu-id="5f87d-396">Bitwise AND</span></span> | <span data-ttu-id="5f87d-397">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5f87d-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="5f87d-398">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-398">Binary</span></span> | <span data-ttu-id="5f87d-399">Bitvis XOR</span><span class="sxs-lookup"><span data-stu-id="5f87d-399">Bitwise XOR</span></span> | <span data-ttu-id="5f87d-400">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5f87d-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="5f87d-401">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-401">Binary</span></span> | <span data-ttu-id="5f87d-402">Bitvis eller</span><span class="sxs-lookup"><span data-stu-id="5f87d-402">Bitwise OR</span></span> | <span data-ttu-id="5f87d-403">`Int` eller `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5f87d-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="5f87d-404">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-404">Binary</span></span> | <span data-ttu-id="5f87d-405">Logiskt AND</span><span class="sxs-lookup"><span data-stu-id="5f87d-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="5f87d-406">Binär</span><span class="sxs-lookup"><span data-stu-id="5f87d-406">Binary</span></span> | <span data-ttu-id="5f87d-407">Logiskt OR</span><span class="sxs-lookup"><span data-stu-id="5f87d-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="5f87d-408">Binär/ternär</span><span class="sxs-lookup"><span data-stu-id="5f87d-408">Binary/Ternary</span></span> | <span data-ttu-id="5f87d-409">Intervall operator</span><span class="sxs-lookup"><span data-stu-id="5f87d-409">Range operator</span></span> | `Int`
 <span data-ttu-id="5f87d-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="5f87d-410">`?` `|`</span></span> | <span data-ttu-id="5f87d-411">Ternär</span><span class="sxs-lookup"><span data-stu-id="5f87d-411">Ternary</span></span> | <span data-ttu-id="5f87d-412">Villkorsstyrd</span><span class="sxs-lookup"><span data-stu-id="5f87d-412">Conditional</span></span> | <span data-ttu-id="5f87d-413">`Bool`för den vänstra sidan</span><span class="sxs-lookup"><span data-stu-id="5f87d-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="5f87d-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="5f87d-414">`w/` `<-`</span></span> | <span data-ttu-id="5f87d-415">Ternär</span><span class="sxs-lookup"><span data-stu-id="5f87d-415">Ternary</span></span> | <span data-ttu-id="5f87d-416">Kopiera och uppdatera</span><span class="sxs-lookup"><span data-stu-id="5f87d-416">Copy-and-update</span></span> | <span data-ttu-id="5f87d-417">Se [Kopiera och uppdatera uttryck](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="5f87d-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="5f87d-418">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5f87d-418">Next steps</span></span>

<span data-ttu-id="5f87d-419">Nu när du kan arbeta med uttryck i Q # kan du gå till [åtgärder och funktioner i q #](xref:microsoft.quantum.guide.operationsfunctions) för att lära dig hur du definierar och anropar-åtgärder och-funktioner.</span><span class="sxs-lookup"><span data-stu-id="5f87d-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
