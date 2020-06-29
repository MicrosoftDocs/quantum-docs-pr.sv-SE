---
title: Typer i Q#
description: 'Lär dig mer om de olika typerna som används i programmeringsspråk för Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415294"
---
# <a name="types-in-q"></a><span data-ttu-id="b97cf-103">Typer i Q#</span><span class="sxs-lookup"><span data-stu-id="b97cf-103">Types in Q#</span></span>

<span data-ttu-id="b97cf-104">I den här artikeln beskrivs typ modellen för Q # och syntaxen för att ange och arbeta med typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="b97cf-105">Mer information om hur du skapar och arbetar med uttryck av dessa typer finns i [typ uttryck](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="b97cf-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="b97cf-106">Vi noterar att Q # är ett *starkt inskrivet* språk, så att en noggrann användning av dessa typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.</span><span class="sxs-lookup"><span data-stu-id="b97cf-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="b97cf-107">För att ge de starkaste garantier som är möjliga, måste konverteringar mellan typer i Q # explicit använda anrop till funktioner som uttrycker konverteringen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="b97cf-108">Q # innehåller en rad olika funktioner som en del av <xref:microsoft.quantum.convert> namn området.</span><span class="sxs-lookup"><span data-stu-id="b97cf-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="b97cf-109">Omsändningar till kompatibla typer, å andra sidan, sker implicit.</span><span class="sxs-lookup"><span data-stu-id="b97cf-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="b97cf-110">Q # tillhandahåller båda primitiva typer, som används direkt och en mängd olika sätt att skapa nya typer av från andra typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="b97cf-111">Vi beskriver var och en i resten av den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b97cf-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="b97cf-112">Primitiva typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-112">Primitive Types</span></span>

<span data-ttu-id="b97cf-113">Q #-språket innehåller följande *primitiva typer*, som du kan använda direkt i Q #-program.</span><span class="sxs-lookup"><span data-stu-id="b97cf-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="b97cf-114">Du kan också använda dessa primitiva typer för att skapa nya typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="b97cf-115">`Int`Typen representerar ett 64-bitars heltal, till exempel,, `2` `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="b97cf-116">`BigInt`Typen representerar ett signerat heltal av godtycklig storlek, till exempel, `2L` , `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="b97cf-117">Den här typen baseras på .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="b97cf-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="b97cf-118">bastyp.</span><span class="sxs-lookup"><span data-stu-id="b97cf-118">type.</span></span>

- <span data-ttu-id="b97cf-119">`Double`Typen representerar ett flyttal med dubbel precision, till exempel,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="b97cf-120">`Bool`Typen representerar ett booleskt värde för antingen `true` eller `false` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="b97cf-121">`Range`Typen representerar en sekvens med heltal, som betecknas av `start..step..stop` , där det är valfritt att ange steget.</span><span class="sxs-lookup"><span data-stu-id="b97cf-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="b97cf-122">`start .. stop`Motsvarar exempelvis `start..1..stop` , och `1..2..7` representerar sekvensen $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="b97cf-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="b97cf-123">`String`Typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="b97cf-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="b97cf-124">Använd `string` typen för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.</span><span class="sxs-lookup"><span data-stu-id="b97cf-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="b97cf-125">`Unit`Typen kan bara ha ett värde, `()` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="b97cf-126">Använd den här typen för att indikera att en Q #-funktion eller-åtgärd returnerar ingen information.</span><span class="sxs-lookup"><span data-stu-id="b97cf-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="b97cf-127">`Qubit`Typen representerar en Quantum-bit eller en qubit.</span><span class="sxs-lookup"><span data-stu-id="b97cf-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="b97cf-128">`Qubit`s är ogenomskinlig för användaren.</span><span class="sxs-lookup"><span data-stu-id="b97cf-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="b97cf-129">Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).</span><span class="sxs-lookup"><span data-stu-id="b97cf-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="b97cf-130">Slutligen implementerar du åtgärder på `Qubit` s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en Quantum-Simulator).</span><span class="sxs-lookup"><span data-stu-id="b97cf-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="b97cf-131">`Pauli`Typen representerar en av de fyra Pauli-operatörerna med en-qubit.</span><span class="sxs-lookup"><span data-stu-id="b97cf-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="b97cf-132">Använd den här typen för att beteckna bas operationen för rotationer och för att ange den som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="b97cf-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="b97cf-133">Det är en uppräknings typ som har fyra möjliga värden: `PauliI` , `PauliX` , `PauliY` och `PauliZ` , som är konstanter av typen `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="b97cf-134">`Result`Typen representerar resultatet av ett mått.</span><span class="sxs-lookup"><span data-stu-id="b97cf-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="b97cf-135">Det är en uppräknad typ med två möjliga värden: `One` och `Zero` , som är konstanter av typen `Result` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="b97cf-136">`Zero`anger att + 1-eigenvalue mättes; `One`anger att-1-eigenvalue mättes.</span><span class="sxs-lookup"><span data-stu-id="b97cf-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="b97cf-137">Konstanterna,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` och `Zero` är alla reserverade symboler i Q #.</span><span class="sxs-lookup"><span data-stu-id="b97cf-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="b97cf-138">Mat ris typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-138">Array Types</span></span>

* <span data-ttu-id="b97cf-139">För en giltig Q #-typ finns en typ som representerar en matris med värden av den typen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="b97cf-140">Till exempel `Qubit[]` och `(Bool, Pauli)[]` representerar matriser med `Qubit` värden och tuple- `(Bool, Pauli)` värden.</span><span class="sxs-lookup"><span data-stu-id="b97cf-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="b97cf-141">En matris med matriser är också giltig.</span><span class="sxs-lookup"><span data-stu-id="b97cf-141">An array of arrays is also valid.</span></span> <span data-ttu-id="b97cf-142">Om du expanderar i föregående exempel visas en matris med `(Bool, Pauli)` matriser `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="b97cf-143">Det här exemplet `(Bool, Pauli)[][]` representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris.</span><span class="sxs-lookup"><span data-stu-id="b97cf-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="b97cf-144">Q # stöder inte rektangulära flerdimensionella matriser.</span><span class="sxs-lookup"><span data-stu-id="b97cf-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="b97cf-145">Ett mat ris värde kan skrivas i Q #-källkod med hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="b97cf-146">Den gemensamma bastypen för alla objekt i matrisen bestämmer typen för en mat ris sträng.</span><span class="sxs-lookup"><span data-stu-id="b97cf-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="b97cf-147">Därför genererar en matris med element som inte har någon common-bastyp ett fel.</span><span class="sxs-lookup"><span data-stu-id="b97cf-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="b97cf-148">Ett exempel finns i [matriser med callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="b97cf-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="b97cf-149">När du har skapat en matris kan du inte ändra elementen i en matris.</span><span class="sxs-lookup"><span data-stu-id="b97cf-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="b97cf-150">Om du vill skapa en modifierad matris använder du instruktioner för att [Uppdatera och omtilldela](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) , eller [Kopiera och uppdatera uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="b97cf-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="b97cf-151">Du kan också skapa en matris från dess storlek med hjälp av `new` nyckelordet:</span><span class="sxs-lookup"><span data-stu-id="b97cf-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="b97cf-152">Använd funktionen Core `Length` för att hämta antalet element från en matris som en `Int` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="b97cf-153">Matriser kan vara nedsänkta för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.</span><span class="sxs-lookup"><span data-stu-id="b97cf-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="b97cf-154">Nedsänkta matriser är noll-baserade och måste vara av typ `Int` eller typ `Range` :</span><span class="sxs-lookup"><span data-stu-id="b97cf-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="b97cf-155">Tuple-typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-155">Tuple Types</span></span>

<span data-ttu-id="b97cf-156">Tupler är ett kraftfullt koncept som används i Q # för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.</span><span class="sxs-lookup"><span data-stu-id="b97cf-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="b97cf-157">I synnerhet kan du använda tupel-notation för att uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.</span><span class="sxs-lookup"><span data-stu-id="b97cf-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="b97cf-158">För noll eller flera olika typer `T0` , `T1` ,..., `Tn` kan du *Ange* en ny tupel som `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="b97cf-159">De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="b97cf-160">Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.</span><span class="sxs-lookup"><span data-stu-id="b97cf-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="b97cf-161">Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="b97cf-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="b97cf-162">Är till exempel `(3, false)` en tupel vars typ är Tuple-typen `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="b97cf-163">Det är möjligt att skapa matriser av tupler, tupler av matriser, tupler av under tupler och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b97cf-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="b97cf-164">Från och med Q # 0,3, `Unit` är namnet på den tomma tupelens *typ* , `()` används som *värde* för den tomma tuppeln.</span><span class="sxs-lookup"><span data-stu-id="b97cf-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="b97cf-165">Tupel-instanser är oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="b97cf-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="b97cf-166">Q # innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="b97cf-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="b97cf-167">Jämförelse av singleton-tupel</span><span class="sxs-lookup"><span data-stu-id="b97cf-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="b97cf-168">Det går att skapa en singleton-tupel (Single-element) `('T1)` , till exempel `(5)` eller `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="b97cf-169">Q # behandlar dock en singleton-tupel som motsvarar ett värde för den omslutna typen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="b97cf-170">Det innebär att det inte finns någon skillnad mellan `5` och `(5)` , eller mellan `5` och `(((5)))` , eller mellan `(5, (6))` och `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="b97cf-171">Det är bara giltigt att skriva `(5)+3` som det är att skriva `5+3` . båda uttrycken utvärderas till `8` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="b97cf-172">Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.</span><span class="sxs-lookup"><span data-stu-id="b97cf-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="b97cf-173">Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.</span><span class="sxs-lookup"><span data-stu-id="b97cf-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="b97cf-174">Till exempel `(7)` är ett uttryck av typen `Int` , `([1,2,3])` är ett uttryck av typen `Int[]` och `((1,2))` är ett uttryck av typen `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="b97cf-175">Det innebär framför allt att du kan visa en åtgärd eller funktion vars typ av tupel eller utgående tuple-typ har ett fält som ett enda argument eller returnerar ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="b97cf-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="b97cf-176">Vi refererar till denna egenskap som _likhet med singleton-tupel_.</span><span class="sxs-lookup"><span data-stu-id="b97cf-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="b97cf-177">Användardefinierade typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-177">User-Defined Types</span></span>

<span data-ttu-id="b97cf-178">En användardefinierad typ deklaration består av nyckelordet `newtype` , följt av namnet på den användardefinierade typen, en `=` , en giltig typ specifikation och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="b97cf-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="b97cf-179">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b97cf-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="b97cf-180">Varje Q #-källfil kan deklarera ett valfritt antal användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="b97cf-181">Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.</span><span class="sxs-lookup"><span data-stu-id="b97cf-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="b97cf-182">Användardefinierade typer är distinkta, även om bas typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="b97cf-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="b97cf-183">I synnerhet finns det ingen automatisk konvertering mellan värdena för två användardefinierade typer, även om de underliggande typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="b97cf-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="b97cf-184">Namngivna kontra anonyma objekt</span><span class="sxs-lookup"><span data-stu-id="b97cf-184">Named vs. anonymous items</span></span>

<span data-ttu-id="b97cf-185">En Q #-fil kan definiera en ny namngiven typ som innehåller ett enda värde av juridisk typ.</span><span class="sxs-lookup"><span data-stu-id="b97cf-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="b97cf-186">För vilken typ `T` av tupel som helst kan du deklarera en ny användardefinierad typ som är en undertyp till `T` `newtype` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="b97cf-187">I @"microsoft.quantum.math" namn rymden definieras exempelvis komplexa tal som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="b97cf-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="b97cf-188">Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="b97cf-189">Förutom anonyma objekt stöder användardefinierade typer också *namngivna objekt* från och med Q # version 0,7 eller högre.</span><span class="sxs-lookup"><span data-stu-id="b97cf-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="b97cf-190">Du kan till exempel namnge objekten till `Re` för det dubbla som representerar den verkliga delen av ett komplext tal och `Im` för den imaginära delen:</span><span class="sxs-lookup"><span data-stu-id="b97cf-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b97cf-191">Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds.</span><span class="sxs-lookup"><span data-stu-id="b97cf-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="b97cf-192">Dessutom kan inre objekt också namnges.</span><span class="sxs-lookup"><span data-stu-id="b97cf-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="b97cf-193">Typen `Nested` , som definieras nedan, till exempel har en underliggande typ `(Double, (Int, String))` , varav endast objekt av typen `Int` heter, och alla andra objekt är anonyma.</span><span class="sxs-lookup"><span data-stu-id="b97cf-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="b97cf-194">Namngivna objekt har fördelen att de kan nås direkt via *åtkomst operatören* `::` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="b97cf-195">Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="b97cf-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="b97cf-196">Till exempel på `Complex` , en kan också ha definierat 2D polär-koordinater som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="b97cf-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="b97cf-197">Även om både `Complex` och `Polar` båda har en underliggande typ `(Double, Double)` , är de två typerna helt inkompatibla i Q #, vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.</span><span class="sxs-lookup"><span data-stu-id="b97cf-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="b97cf-198">Komma åt anonyma objekt med unwrap-operatorn</span><span class="sxs-lookup"><span data-stu-id="b97cf-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="b97cf-199">För att komma åt anonyma objekt, extrahera först det omslutna värdet med hjälp av postfix-operatorn `!` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="b97cf-200">Med operatorn "unwrap" `!` kan du extrahera värdet som finns i en användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="b97cf-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="b97cf-201">Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="b97cf-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="b97cf-202">En enda unwrap-operator avbryter ett rad brytnings lager.</span><span class="sxs-lookup"><span data-stu-id="b97cf-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="b97cf-203">Använd flera unwrap-operatorer för att få åtkomst till ett multiplicerat rad värde.</span><span class="sxs-lookup"><span data-stu-id="b97cf-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="b97cf-204">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b97cf-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="b97cf-205">Mer information om unwrap-operatorn finns i [Skriv uttryck i Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="b97cf-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="b97cf-206">Skapa värden av användardefinierade typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-206">Creating values of user-defined types</span></span>

<span data-ttu-id="b97cf-207">Skapa värden för en användardefinierad typ genom att anropa motsvarande typ-konstruktor:</span><span class="sxs-lookup"><span data-stu-id="b97cf-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="b97cf-208">Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="b97cf-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="b97cf-209">Precis som med matriser kopierar och uppdaterar uttryck alla objekt värden för det ursprungliga uttrycket, förutom de angivna namngivna objekten.</span><span class="sxs-lookup"><span data-stu-id="b97cf-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="b97cf-210">För dessa undantag är värdena för dessa objekt de värden som definieras på höger sida av uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b97cf-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="b97cf-211">Andra språk konstruktioner som är tillgängliga för mat ris objekt, till exempel [Update-och-Reassign-instruktioner](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), finns för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="b97cf-212">Du kan använda användardefinierade typer överallt där du använder andra typer av typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="b97cf-213">I synnerhet är det möjligt att definiera en matris av en användardefinierad typ och för att inkludera en användardefinierad typ som ett element av en tupel-typ.</span><span class="sxs-lookup"><span data-stu-id="b97cf-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="b97cf-214">Det går inte att skapa rekursiva typ strukturer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="b97cf-215">Det vill säga den typ som definierar en användardefinierad typ kan inte vara en tupel som innehåller ett element av den användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="b97cf-216">I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning av typ definitioner är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="b97cf-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="b97cf-217">Åtgärds-och funktions typer</span><span class="sxs-lookup"><span data-stu-id="b97cf-217">Operation and Function Types</span></span>

<span data-ttu-id="b97cf-218">Utifrån typerna `'Tinput` och `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="b97cf-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="b97cf-219">`('Tinput => 'Tresult)`är den grundläggande typen för alla *åtgärder*, till exempel `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="b97cf-220">`('Tinput -> 'Tresult)`är den grundläggande typen för alla *funktioner*, till exempel `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="b97cf-221">Dessa kallas *signaturen* för anropbar.</span><span class="sxs-lookup"><span data-stu-id="b97cf-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="b97cf-222">Alla Q # callables tar ett enda värde som indata och returnerar ett enda värde som utdata.</span><span class="sxs-lookup"><span data-stu-id="b97cf-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="b97cf-223">Du kan använda tupler för både in-och utdata-värden.</span><span class="sxs-lookup"><span data-stu-id="b97cf-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="b97cf-224">Callables som inte har något resultat returneras `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="b97cf-225">Callables som inte har något inmatade tar den tomma tuppeln som inmatad.</span><span class="sxs-lookup"><span data-stu-id="b97cf-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="b97cf-226">Functors</span><span class="sxs-lookup"><span data-stu-id="b97cf-226">Functors</span></span>

<span data-ttu-id="b97cf-227">*Funktions* typer anges fullständigt av signaturen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="b97cf-228">En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="b97cf-229">*Åtgärder* har vissa ytterligare egenskaper som uttrycks som en del av åtgärds typen.</span><span class="sxs-lookup"><span data-stu-id="b97cf-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="b97cf-230">Dessa egenskaper innehåller information om vilka *functors* som stöds av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="b97cf-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="b97cf-231">Om till exempel körningen av åtgärden förlitar sig på andra qubits-tillstånd, måste den ha stöd för `Controlled` Functor. om åtgärden har ett Inverse ska den ha stöd för `Adjoint` Functor.</span><span class="sxs-lookup"><span data-stu-id="b97cf-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="b97cf-232">Den här artikeln beskriver endast hur functors ändrar signaturen för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="b97cf-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="b97cf-233">Mer information om functors och åtgärder finns [i åtgärder och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b97cf-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="b97cf-234">Om du behöver stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ måste du lägga till en anteckning som anger motsvarande egenskaper.</span><span class="sxs-lookup"><span data-stu-id="b97cf-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="b97cf-235">Anteckningen `is Ctl` (till exempel `(Qubit => Unit is Ctl)` ) visar att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="b97cf-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="b97cf-236">Det vill säga att dess körning är beroende av statusen för en annan qubit eller qubits.</span><span class="sxs-lookup"><span data-stu-id="b97cf-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="b97cf-237">På samma sätt betyder anteckningen `is Adj` att åtgärden har ett överordnat objekt, det vill säga att den kan vara "inverterad", så att en åtgärd som sedan är i det angränsande till ett tillstånd lämnar statusen oförändrad.</span><span class="sxs-lookup"><span data-stu-id="b97cf-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="b97cf-238">Om du vill kräva att en åtgärd av den typen stöder både- `Adjoint` och `Controlled` Functor kan du uttrycka detta som `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="b97cf-239">Den inbyggda Pauli-åtgärden har till exempel <xref:microsoft.quantum.intrinsic.x> typen `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="b97cf-240">En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.</span><span class="sxs-lookup"><span data-stu-id="b97cf-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="b97cf-241">Typ-parameter funktioner och åtgärder</span><span class="sxs-lookup"><span data-stu-id="b97cf-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="b97cf-242">Typer som kan anropas kan innehålla *typ parametrar*.</span><span class="sxs-lookup"><span data-stu-id="b97cf-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="b97cf-243">Använd en symbol som föregås av ett enkelt citat tecken för att indikera en typ parameter. till exempel `'A` är en juridisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="b97cf-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="b97cf-244">Mer information och information om hur du definierar callables för typ parametrar finns [i åtgärder och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="b97cf-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="b97cf-245">En typ parameter kan visas mer än en gång i en enda signatur.</span><span class="sxs-lookup"><span data-stu-id="b97cf-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="b97cf-246">Till exempel en funktion som tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signaturen `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="b97cf-247">På samma sätt har en funktion som returnerar kompositionen av två åtgärder signaturen `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="b97cf-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="b97cf-248">När du anropar en typ-parameter anrops bara måste alla argument som har samma typ parameter vara av samma typ.</span><span class="sxs-lookup"><span data-stu-id="b97cf-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="b97cf-249">Q # innehåller ingen mekanism för att begränsa de möjliga typer som en användare kan ersätta för en typ parameter.</span><span class="sxs-lookup"><span data-stu-id="b97cf-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b97cf-250">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b97cf-250">Next steps</span></span>

<span data-ttu-id="b97cf-251">Nu när du har sett alla typer som ingår i Q #-språket, se [text uttryck i Q #](xref:microsoft.quantum.guide.expressions) för att lära dig hur du skapar och ändrar uttryck för dessa olika typer.</span><span class="sxs-lookup"><span data-stu-id="b97cf-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
