---
title: Typer i Q#
description: 'Lär dig mer om de olika typerna som används i programmeringsspråk för Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327296"
---
# <a name="types-in-q"></a><span data-ttu-id="444fd-103">Typer i Q#</span><span class="sxs-lookup"><span data-stu-id="444fd-103">Types in Q#</span></span>

<span data-ttu-id="444fd-104">På den här sidan får du en modell av typen Q # och beskriver syntaxen för att ange och arbeta med typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="444fd-105">Nästa sida, [Skriv uttryck](xref:microsoft.quantum.guide.expressions), information om hur du skapar och arbetar med uttryck av dessa typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="444fd-106">Vi noterar att Q # är ett *starkt inskrivet* språk, så att en noggrann användning av dessa typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.</span><span class="sxs-lookup"><span data-stu-id="444fd-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="444fd-107">För att tillhandahålla starkast möjliga garantier är konverteringar mellan typer i Q # explicita med anrop till funktioner som uttrycker konverteringen.</span><span class="sxs-lookup"><span data-stu-id="444fd-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="444fd-108">En rad olika funktioner tillhandahålls som en del av <xref:microsoft.quantum.convert> namn området.</span><span class="sxs-lookup"><span data-stu-id="444fd-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="444fd-109">Omsändningar till kompatibla typer av andra händer implicit.</span><span class="sxs-lookup"><span data-stu-id="444fd-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="444fd-110">Q # tillhandahåller båda primitiva typer, som kan användas direkt och en mängd olika sätt att skapa nya typer från andra typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="444fd-111">Vi beskriver var och en i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="444fd-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="444fd-112">Primitiva typer</span><span class="sxs-lookup"><span data-stu-id="444fd-112">Primitive Types</span></span>

<span data-ttu-id="444fd-113">Q #-språket innehåller flera *primitiva typer*, från vilka andra typer kan konstrueras:</span><span class="sxs-lookup"><span data-stu-id="444fd-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="444fd-114">`Int`Typen representerar ett 64-bitars heltal, t. ex.: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="444fd-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="444fd-115">`BigInt`Typen representerar ett signerat heltal av godtycklig storlek, t. ex., `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="444fd-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="444fd-116">Den här typen baseras på .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="444fd-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="444fd-117">bastyp.</span><span class="sxs-lookup"><span data-stu-id="444fd-117">type.</span></span>
- <span data-ttu-id="444fd-118">`Double`Typen representerar ett flyttal med dubbel precision, t. ex.: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="444fd-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="444fd-119">`Bool`Typen representerar ett booleskt värde som antingen kan vara `true` eller `false` .</span><span class="sxs-lookup"><span data-stu-id="444fd-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="444fd-120">`Range`Typen representerar en sekvens med heltal, som betecknas av `start..step..stop` , där det är valfritt att ange steget.</span><span class="sxs-lookup"><span data-stu-id="444fd-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="444fd-121">Detta `start .. stop` motsvarar `start..1..stop` , och t. ex. `1..2..7` representerar sekvensen $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="444fd-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="444fd-122">`String`Typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="444fd-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="444fd-123">Den här typen används för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.</span><span class="sxs-lookup"><span data-stu-id="444fd-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="444fd-124">`Unit`Typen är den typ som endast tillåter ett värde `()` .</span><span class="sxs-lookup"><span data-stu-id="444fd-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="444fd-125">Den här typen används för att indikera att funktionen Q # Function eller operation returnerar ingen information.</span><span class="sxs-lookup"><span data-stu-id="444fd-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="444fd-126">`Qubit`Typen representerar en Quantum-bit eller en qubit.</span><span class="sxs-lookup"><span data-stu-id="444fd-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="444fd-127">`Qubit`s är ogenomskinlig för användaren. Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).</span><span class="sxs-lookup"><span data-stu-id="444fd-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="444fd-128">Slutligen `Qubit` implementeras åtgärder på s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en simulering av detta).</span><span class="sxs-lookup"><span data-stu-id="444fd-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="444fd-129">`Pauli`Typen representerar en av de fyra Pauli-operatörerna med en-qubit.</span><span class="sxs-lookup"><span data-stu-id="444fd-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="444fd-130">Den här typen används för att beteckna bas operationen för rotationer och för att ange den som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="444fd-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="444fd-131">Detta är en uppräknings typ som har fyra möjliga värden: `PauliI` , `PauliX` , `PauliY` och `PauliZ` , som är konstanter av typen `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="444fd-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="444fd-132">`Result`Typen representerar resultatet av ett mått.</span><span class="sxs-lookup"><span data-stu-id="444fd-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="444fd-133">Detta är en uppräknings typ med två möjliga värden: `One` och `Zero` , som är konstanter av typen `Result` .</span><span class="sxs-lookup"><span data-stu-id="444fd-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="444fd-134">`Zero`anger att + 1-eigenvalue mättes; `One`anger-1-eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="444fd-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="444fd-135">Konstanterna,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` och `Zero` är alla reserverade symboler i Q #.</span><span class="sxs-lookup"><span data-stu-id="444fd-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="444fd-136">Mat ris typer</span><span class="sxs-lookup"><span data-stu-id="444fd-136">Array Types</span></span>

<span data-ttu-id="444fd-137">Med en giltig Q #-typ finns `'T` en typ som representerar en matris med värden av typen `'T` .</span><span class="sxs-lookup"><span data-stu-id="444fd-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="444fd-138">Den här mat ris typen visas som `'T[]` till exempel `Qubit[]` eller `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="444fd-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="444fd-139">Till exempel är en samling av heltal som anges `Int[]` , medan en matris med `(Bool, Pauli)` värden anges `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="444fd-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="444fd-140">I det andra exemplet noterar du att detta representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris.</span><span class="sxs-lookup"><span data-stu-id="444fd-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="444fd-141">Q # ger inte stöd för rektangulära flerdimensionella matriser.</span><span class="sxs-lookup"><span data-stu-id="444fd-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="444fd-142">Ett mat ris värde kan skrivas i Q #-källkod med hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="444fd-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="444fd-143">Typen av mat ris literal bestäms av den gemensamma bastypen för alla objekt i matrisen.</span><span class="sxs-lookup"><span data-stu-id="444fd-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> <span data-ttu-id="444fd-144">Att försöka skapa en matris med element som inte har någon gemensam bastyp kommer att generera ett fel.</span><span class="sxs-lookup"><span data-stu-id="444fd-144">Hence trying to construct an array with elements that have no common base type will raise an error.</span></span>  
<span data-ttu-id="444fd-145">Ett exempel på detta finns i [matriser med callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables) .</span><span class="sxs-lookup"><span data-stu-id="444fd-145">See [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables) for an example of this.</span></span>

> [!WARNING]
> <span data-ttu-id="444fd-146">Elementen i en matris kan inte ändras efter att matrisen har skapats.</span><span class="sxs-lookup"><span data-stu-id="444fd-146">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="444fd-147">Du kan använda uttryck för att [Uppdatera och omtilldela](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) och/eller [Kopiera och uppdatera](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) för att skapa en modifierad matris.</span><span class="sxs-lookup"><span data-stu-id="444fd-147">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="444fd-148">Du kan också skapa en matris från dess storlek med hjälp av `new` nyckelordet:</span><span class="sxs-lookup"><span data-stu-id="444fd-148">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="444fd-149">I båda fallen kan funktionen Core `Length` användas för att hämta antalet element som ett när en matris har konstruerats `Int` .</span><span class="sxs-lookup"><span data-stu-id="444fd-149">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="444fd-150">Matriser kan skrivas med hakparenteser med hjälp av nedsänkta hakparenteser, som antingen har typ `Int` eller typ `Range` , för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.</span><span class="sxs-lookup"><span data-stu-id="444fd-150">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="444fd-151">Under skripten för matriser är noll-baserade:</span><span class="sxs-lookup"><span data-stu-id="444fd-151">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="444fd-152">Tuple-typer</span><span class="sxs-lookup"><span data-stu-id="444fd-152">Tuple Types</span></span>

<span data-ttu-id="444fd-153">För noll eller flera olika typer `T0` , `T1` ,..., `Tn` kan vi *Ange* en ny tupel som `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-153">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="444fd-154">De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="444fd-154">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="444fd-155">Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.</span><span class="sxs-lookup"><span data-stu-id="444fd-155">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="444fd-156">Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="444fd-156">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="444fd-157">Är till exempel `(3, false)` en tupel vars typ är Tuple-typen `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-157">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="444fd-158">Det går att skapa matriser av tupler, tupler av matriser, tupler av under tupler osv.</span><span class="sxs-lookup"><span data-stu-id="444fd-158">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="444fd-159">Från och med Q # 0,3, `Unit` är namnet på den tomma tupelens *typ* , `()` används för det tomma tuple- *värdet*.</span><span class="sxs-lookup"><span data-stu-id="444fd-159">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="444fd-160">Tupel-instanser är oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="444fd-160">Tuple instances are immutable.</span></span>
<span data-ttu-id="444fd-161">Q # innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="444fd-161">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="444fd-162">Tupler är ett kraftfullt koncept som används i Q # för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.</span><span class="sxs-lookup"><span data-stu-id="444fd-162">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="444fd-163">I synnerhet kan vi, om du använder tupel notation, uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.</span><span class="sxs-lookup"><span data-stu-id="444fd-163">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="444fd-164">Jämförelse av singleton-tupel</span><span class="sxs-lookup"><span data-stu-id="444fd-164">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="444fd-165">Det går att skapa en singleton-tupel (Single-element), `('T1)` till exempel `(5)` eller `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="444fd-165">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="444fd-166">Q # behandlar dock en singleton-tupel som är helt likvärdig med värdet för den omslutna typen.</span><span class="sxs-lookup"><span data-stu-id="444fd-166">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="444fd-167">Det innebär att det inte finns någon skillnad mellan `5` och `(5)` , eller mellan `5` och `(((5)))` , eller mellan `(5, (6))` och `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-167">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="444fd-168">Det är precis som giltigt för att skriva `(5)+3` till Skriv `5+3` och båda uttrycken kommer att utvärderas till `8` .</span><span class="sxs-lookup"><span data-stu-id="444fd-168">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="444fd-169">Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.</span><span class="sxs-lookup"><span data-stu-id="444fd-169">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="444fd-170">Detta uttryck har fått ett uttryck av samma typ, i alla uttryck.</span><span class="sxs-lookup"><span data-stu-id="444fd-170">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="444fd-171">Är till exempel `(7)` ett `Int` uttryck, `([1,2,3])` är ett uttryck av typen matris för `Int` s och `((1,2))` är ett uttryck med typen `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-171">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="444fd-172">Det innebär särskilt att en åtgärd eller funktion vars typ av tupel eller utgående tuple har ett fält kan betraktas som ett enda argument eller returnerar ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="444fd-172">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="444fd-173">Vi refererar till denna egenskap som _likhet med singleton-tupel_.</span><span class="sxs-lookup"><span data-stu-id="444fd-173">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="444fd-174">Användardefinierade typer</span><span class="sxs-lookup"><span data-stu-id="444fd-174">User-Defined Types</span></span>

<span data-ttu-id="444fd-175">En användardefinierad typ deklaration består av nyckelordet `newtype` , följt av namnet på den användardefinierade typen, en `=` , en giltig typ specifikation och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="444fd-175">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="444fd-176">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="444fd-176">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="444fd-177">Varje Q #-källfil kan deklarera ett valfritt antal användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-177">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="444fd-178">Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.</span><span class="sxs-lookup"><span data-stu-id="444fd-178">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="444fd-179">Användardefinierade typer är distinkta även om bas typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="444fd-179">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="444fd-180">I synnerhet finns det ingen automatisk konvertering mellan värden av två användardefinierade typer, även om de underliggande typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="444fd-180">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="444fd-181">Namngivna kontra anonyma objekt</span><span class="sxs-lookup"><span data-stu-id="444fd-181">Named vs. anonymous items</span></span>

<span data-ttu-id="444fd-182">En Q #-fil kan definiera en ny namngiven typ som innehåller ett enda värde av juridisk typ.</span><span class="sxs-lookup"><span data-stu-id="444fd-182">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="444fd-183">För alla typer av tupler `T` kan vi deklarera en ny användardefinierad typ som är en undertyp till `T` `newtype` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="444fd-183">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="444fd-184">I @"microsoft.quantum.math" namn rymden definieras exempelvis komplexa tal som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="444fd-184">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="444fd-185">Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double` .</span><span class="sxs-lookup"><span data-stu-id="444fd-185">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="444fd-186">Förutom anonyma objekt stöder användardefinierade typer också *namngivna objekt* från och med Q # version 0,7 eller högre.</span><span class="sxs-lookup"><span data-stu-id="444fd-186">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="444fd-187">Vi kan till exempel ha namngett till-objekten `Re` för det dubbla som representerar den verkliga delen av ett komplext tal och `Im` för den imaginära delen:</span><span class="sxs-lookup"><span data-stu-id="444fd-187">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="444fd-188">Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds.</span><span class="sxs-lookup"><span data-stu-id="444fd-188">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="444fd-189">Dessutom kan inre objekt också namnges.</span><span class="sxs-lookup"><span data-stu-id="444fd-189">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="444fd-190">Typen `Nested` som definieras nedan har exempelvis en underliggande typ `(Double, (Int, String))` , varav endast objekt av typen `Int` heter och alla andra objekt är anonyma.</span><span class="sxs-lookup"><span data-stu-id="444fd-190">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="444fd-191">Namngivna objekt har fördelen att de kan nås direkt via *åtkomst operatören* `::` .</span><span class="sxs-lookup"><span data-stu-id="444fd-191">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="444fd-192">Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="444fd-192">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="444fd-193">Till exempel på `Complex` , en kan också ha definierat 2D polär-koordinater som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="444fd-193">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="444fd-194">Även om både `Complex` och båda `Polar` har en underliggande typ `(Double, Double)` , är de två typerna helt inkompatibla i Q #, vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.</span><span class="sxs-lookup"><span data-stu-id="444fd-194">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="444fd-195">På så sätt har användardefinierade typer en liknande roll som poster i F # till exempel.</span><span class="sxs-lookup"><span data-stu-id="444fd-195">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="444fd-196">Komma åt anonyma objekt med unwrap-operatorn</span><span class="sxs-lookup"><span data-stu-id="444fd-196">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="444fd-197">För att kunna komma åt anonyma objekt måste det omslutna värdet först extraheras med hjälp av postfix-operatorn `!` .</span><span class="sxs-lookup"><span data-stu-id="444fd-197">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="444fd-198">Med "unwrap"-operatorn kan `!` du extrahera värdet som finns i en användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="444fd-198">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="444fd-199">Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="444fd-199">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="444fd-200">Unwrap-operatorn omger ett exakt rad brytnings lager.</span><span class="sxs-lookup"><span data-stu-id="444fd-200">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="444fd-201">Flera unwrap-operatorer kan användas för att få åtkomst till ett multiplicering-figursatt värde.</span><span class="sxs-lookup"><span data-stu-id="444fd-201">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="444fd-202">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="444fd-202">For instance:</span></span>

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

<span data-ttu-id="444fd-203">Du hittar mer information om unwrap-operatorn [i typ uttryck i Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="444fd-203">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="444fd-204">Skapa värden av användardefinierade typer</span><span class="sxs-lookup"><span data-stu-id="444fd-204">Creating values of user-defined types</span></span>

<span data-ttu-id="444fd-205">Värden för en användardefinierad typ kan skapas genom att anropa motsvarande typ av konstruktor:</span><span class="sxs-lookup"><span data-stu-id="444fd-205">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="444fd-206">Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="444fd-206">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="444fd-207">Precis som för matriser kopierar sådana uttryck alla objekt värden för det ursprungliga uttrycket, med undantag för de angivna namngivna objekten.</span><span class="sxs-lookup"><span data-stu-id="444fd-207">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="444fd-208">För dessa värden anges de som definierats till höger i uttrycket.</span><span class="sxs-lookup"><span data-stu-id="444fd-208">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="444fd-209">Andra språk konstruktioner, t. ex. [uppdaterings-och omtilldelnings instruktioner](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), som är tillgängliga för mat ris objekt, finns även för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-209">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="444fd-210">Användardefinierade typer kan användas var som helst av andra typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-210">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="444fd-211">I synnerhet är det möjligt att definiera en matris av en användardefinierad typ och för att inkludera en användardefinierad typ som ett element av en tupel-typ.</span><span class="sxs-lookup"><span data-stu-id="444fd-211">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="444fd-212">Obs! det går inte att skapa rekursiva typ strukturer.</span><span class="sxs-lookup"><span data-stu-id="444fd-212">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="444fd-213">Det vill säga den typ som definierar en användardefinierad typ får inte vara en tuple-typ som innehåller ett element av den användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="444fd-213">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="444fd-214">I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning typ definitioner skulle vara ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="444fd-214">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="444fd-215">Åtgärds-och funktions typer</span><span class="sxs-lookup"><span data-stu-id="444fd-215">Operation and Function Types</span></span>

<span data-ttu-id="444fd-216">Den grundläggande typen för anrop är skriven som `('Tinput => 'Tresult)` eller `('Tinput -> 'Tresult)` , där både `'Tinput` och `'Tresult` är typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-216">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="444fd-217">Dessa kallas *signaturen* för anropbar.</span><span class="sxs-lookup"><span data-stu-id="444fd-217">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="444fd-218">Alla Q # callables anses ta ett enda värde som indata och returnera ett enda värde som utdata.</span><span class="sxs-lookup"><span data-stu-id="444fd-218">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="444fd-219">Både in-och utdata-värden kan vara tupler.</span><span class="sxs-lookup"><span data-stu-id="444fd-219">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="444fd-220">Callables som inte returnerade resultat `Unit` .</span><span class="sxs-lookup"><span data-stu-id="444fd-220">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="444fd-221">Callables som inte har något inmatade tar den tomma tuppeln som inmatad.</span><span class="sxs-lookup"><span data-stu-id="444fd-221">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="444fd-222">Det första formuläret, med `=>` , används för åtgärder, det andra formuläret, med `->` , för functions.</span><span class="sxs-lookup"><span data-stu-id="444fd-222">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="444fd-223">Till exempel `((Qubit, Pauli) => Result)` representerar signaturen för en möjlig mätnings åtgärd med en qubit.</span><span class="sxs-lookup"><span data-stu-id="444fd-223">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="444fd-224">*Funktions* typer anges fullständigt av signaturen.</span><span class="sxs-lookup"><span data-stu-id="444fd-224">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="444fd-225">En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-225">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="444fd-226">*Åtgärder*---men fungerar inte---ha vissa ytterligare egenskaper som uttrycks som en del av åtgärds typen.</span><span class="sxs-lookup"><span data-stu-id="444fd-226">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="444fd-227">Dessa egenskaper innehåller information om vad *functors* åtgärden stöder.</span><span class="sxs-lookup"><span data-stu-id="444fd-227">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="444fd-228">Om till exempel körning av åtgärden kan konditioneras i andra qubits-tillstånd, måste den ha stöd för `Controlled` Functor. om åtgärden har ett Inverse ska den ha stöd för `Adjoint` Functor.</span><span class="sxs-lookup"><span data-stu-id="444fd-228">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="444fd-229">Functors och åtgärder beskrivs i detalj vid [drift och funktioner i Q #](xref:microsoft.quantum.guide.operationsfunctions), men här diskuterar vi bara hur detta ändrar signaturen för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="444fd-229">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="444fd-230">För att kunna kräva stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ måste vi lägga till en anteckning som anger motsvarande egenskaper.</span><span class="sxs-lookup"><span data-stu-id="444fd-230">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="444fd-231">En anteckning `is Ctl` (t. ex. `(Qubit => Unit is Ctl)` ) visar att åtgärden är kontrollerbar---att den körs i tillståndet för en annan qubit eller qubits.</span><span class="sxs-lookup"><span data-stu-id="444fd-231">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="444fd-232">På samma sätt `is Adj` anger att åtgärden har ett överordnat objekt eller bara kan den vara "inverterad", som att använda en åtgärd och sedan dess angränsande till ett tillstånd lämnar statusen oförändrad.</span><span class="sxs-lookup"><span data-stu-id="444fd-232">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="444fd-233">Om vi vill kräva att en åtgärd av den typen stöder både- `Adjoint` och `Controlled` Functor kan vi uttrycka detta som `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-233">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="444fd-234">Den inbyggda Pauli-åtgärden har till exempel <xref:microsoft.quantum.intrinsic.x> typen `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="444fd-234">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="444fd-235">En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.</span><span class="sxs-lookup"><span data-stu-id="444fd-235">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="444fd-236">Typ-parameter funktioner och åtgärder</span><span class="sxs-lookup"><span data-stu-id="444fd-236">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="444fd-237">Typer som kan anropas kan innehålla typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="444fd-237">Callable types may contain type parameters.</span></span>
<span data-ttu-id="444fd-238">Typ parametrar anges med en symbol som föregås av ett enkelt citat tecken. till exempel `'A` är en juridisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="444fd-238">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="444fd-239">Information om hur du definierar typ Parameters-callables finns på sidan [åtgärder och funktioner på Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .</span><span class="sxs-lookup"><span data-stu-id="444fd-239">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="444fd-240">En typ parameter kan visas mer än en gång i en enda signatur.</span><span class="sxs-lookup"><span data-stu-id="444fd-240">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="444fd-241">En funktion som till exempel tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signatur `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="444fd-241">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="444fd-242">På samma sätt kan en funktion som returnerar sammansättningen av två åtgärder ha signatur `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="444fd-242">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="444fd-243">När du anropar en typ-parameter anrops bara, måste alla argument som har samma typ parameter vara av samma typ.</span><span class="sxs-lookup"><span data-stu-id="444fd-243">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="444fd-244">Q # innehåller ingen mekanism för att begränsa de möjliga typer som kan ersättas av en typ parameter.</span><span class="sxs-lookup"><span data-stu-id="444fd-244">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="444fd-245">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="444fd-245">Next steps</span></span>

<span data-ttu-id="444fd-246">Nu när du har sett alla typer som utgör Q #-språket kan du [Ange uttryck i Q #](xref:microsoft.quantum.guide.expressions) för att se hur du skapar och ändrar uttryck för dessa olika typer.</span><span class="sxs-lookup"><span data-stu-id="444fd-246">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


