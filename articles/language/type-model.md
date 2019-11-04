---
title: 'Q # typ modell | Microsoft Docs'
description: 'Q # typ modell'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184754"
---
# <a name="the-type-model"></a><span data-ttu-id="c28e5-103">Typ modellen</span><span class="sxs-lookup"><span data-stu-id="c28e5-103">The Type Model</span></span>

<span data-ttu-id="c28e5-104">Det här avsnittet innehåller en modell av typen Q # och beskriver syntaxen för att ange och arbeta med typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="c28e5-105">Vi noterar att Q # är ett *starkt inskrivet* språk, så att en noggrann användning av dessa typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.</span><span class="sxs-lookup"><span data-stu-id="c28e5-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="c28e5-106">För att tillhandahålla starkast möjliga garantier är konverteringar mellan typer i Q # explicita med anrop till funktioner som uttrycker konverteringen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="c28e5-107">En rad olika funktioner tillhandahålls som en del av <xref:microsoft.quantum.convert>-namnområdet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="c28e5-108">Omsändningar till kompatibla typer av andra händer implicit.</span><span class="sxs-lookup"><span data-stu-id="c28e5-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="c28e5-109">Q # tillhandahåller båda primitiva typer, som kan användas direkt och en mängd olika sätt att skapa nya typer från andra typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="c28e5-110">Vi beskriver var och en i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="c28e5-111">Primitiva typer</span><span class="sxs-lookup"><span data-stu-id="c28e5-111">Primitive Types</span></span>

<span data-ttu-id="c28e5-112">Q #-språket innehåller flera *primitiva typer*, från vilka andra typer kan konstrueras:</span><span class="sxs-lookup"><span data-stu-id="c28e5-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="c28e5-113">`Int` typen representerar ett 64-bitars heltal, t. ex.: `2`, `107`, `-5`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="c28e5-114">`BigInt` typen representerar ett signerat heltal av godtycklig storlek, t. ex. `2L`, `107L`, `-5L`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="c28e5-115">Den här typen baseras på .NET-<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="c28e5-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="c28e5-116">bastyp.</span><span class="sxs-lookup"><span data-stu-id="c28e5-116">type.</span></span>
- <span data-ttu-id="c28e5-117">`Double` typen representerar ett flyttal med dubbel precision, t. ex.: `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="c28e5-118">`Bool` typen representerar ett booleskt värde som antingen kan vara `true` eller `false`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="c28e5-119">`Qubit` typen representerar en Quantum-bit eller qubit.</span><span class="sxs-lookup"><span data-stu-id="c28e5-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="c28e5-120">`Qubit`s är ogenomskinlig för användaren. Det enda som är möjligt med dem, förutom att skicka dem till en annan åtgärd, är att testa för identitet (likhet).</span><span class="sxs-lookup"><span data-stu-id="c28e5-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="c28e5-121">Slutligen implementeras åtgärder på `Qubit`s genom att anropa inbyggda instruktioner på en Quantum-processor (eller en simulering av detta).</span><span class="sxs-lookup"><span data-stu-id="c28e5-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="c28e5-122">`Pauli` typen representerar en av de fyra Pauli-operatörerna med en qubit.</span><span class="sxs-lookup"><span data-stu-id="c28e5-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="c28e5-123">Den här typen används för att beteckna bas operationen för rotationer och för att ange den som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="c28e5-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="c28e5-124">Detta är en uppräknings typ som har fyra möjliga värden: `PauliI`, `PauliX`, `PauliY`och `PauliZ`, som är konstanter av typen `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="c28e5-125">`Result` typen representerar resultatet av ett mått.</span><span class="sxs-lookup"><span data-stu-id="c28e5-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="c28e5-126">Detta är en uppräknings typ med två möjliga värden: `One` och `Zero`, som är konstanter av typen `Result`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="c28e5-127">`Zero` anger att + 1-eigenvalue mättes. `One` anger-1-eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="c28e5-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="c28e5-128">`Range` typen representerar en sekvens med heltal, som betecknas med `start..step..stop`, där du ser att steget är alternativ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="c28e5-129">Det är `start .. stop` motsvarar `start..1..stop`, och till exempel `1..2..7` representerar sekvensen $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="c28e5-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="c28e5-130">`String` typen är en sekvens med Unicode-tecken som är ogenomskinlig för användaren när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="c28e5-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="c28e5-131">Den här typen används för att rapportera meddelanden till en klassisk-värd om det uppstår ett fel eller en diagnostisk händelse.</span><span class="sxs-lookup"><span data-stu-id="c28e5-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="c28e5-132">`Unit` typen är den typ som endast tillåter ett värde `()`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="c28e5-133">Den här typen används för att indikera att funktionen Q # Function eller operation returnerar ingen information.</span><span class="sxs-lookup"><span data-stu-id="c28e5-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="c28e5-134">Konstanterna `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`och `Zero` är alla reserverade symboler i Q #.</span><span class="sxs-lookup"><span data-stu-id="c28e5-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="c28e5-135">Mat ris typer</span><span class="sxs-lookup"><span data-stu-id="c28e5-135">Array Types</span></span>

<span data-ttu-id="c28e5-136">Med en giltig Q #-typ `'T`, finns en typ som representerar en matris med värden av typen `'T`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="c28e5-137">Den här mat ris typen visas som `'T[]`. till exempel `Qubit[]` eller `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="c28e5-138">Till exempel är en samling med heltal `Int[]`, medan en matris med matriser med `(Bool, Pauli)` värden anges `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="c28e5-139">I det andra exemplet noterar du att detta representerar en potentiellt Taggad matris med matriser och inte en rektangulär tvådimensionell matris.</span><span class="sxs-lookup"><span data-stu-id="c28e5-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="c28e5-140">Q # ger inte stöd för rektangulära flerdimensionella matriser.</span><span class="sxs-lookup"><span data-stu-id="c28e5-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="c28e5-141">Ett mat ris värde kan skrivas i Q #-källkod med hakparenteser runt elementen i en matris, som i `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="c28e5-142">Typen av mat ris literal bestäms av den gemensamma bastypen för alla objekt i matrisen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="c28e5-143">Elementen i en matris kan inte ändras efter att matrisen har skapats.</span><span class="sxs-lookup"><span data-stu-id="c28e5-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="c28e5-144">Du kan använda uttryck för att uppdatera och omtilldela och/eller kopiera och uppdatera för att skapa en modifierad matris.</span><span class="sxs-lookup"><span data-stu-id="c28e5-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="c28e5-145">Du kan också skapa en matris från dess storlek med hjälp av nyckelordet `new`:</span><span class="sxs-lookup"><span data-stu-id="c28e5-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="c28e5-146">I båda fallen kan Core-funktionen `Length` användas för att hämta antalet element som en `Int`när en matris har konstruerats.</span><span class="sxs-lookup"><span data-stu-id="c28e5-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="c28e5-147">Matriser kan användas tillsammans med hakparenteser, med under skript som antingen har typ `Int` eller typ `Range`, för att hämta antingen enstaka element eller nya matriser som innehåller en delmängd av elementen i en matris.</span><span class="sxs-lookup"><span data-stu-id="c28e5-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="c28e5-148">Under skripten för matriser är noll-baserade:</span><span class="sxs-lookup"><span data-stu-id="c28e5-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="c28e5-149">Tuple-typer</span><span class="sxs-lookup"><span data-stu-id="c28e5-149">Tuple Types</span></span>

<span data-ttu-id="c28e5-150">För noll eller flera olika typer `T0`, `T1`,..., `Tn`, kan vi ange en ny *typ av tupel* som `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="c28e5-151">De typer som används för att skapa en ny tupel-typ kan själva vara tupleer, som i `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="c28e5-152">Sådan kapsling är alltid begränsad, men eftersom tuple-typer inte kan under några omständigheter innehålla sig själva.</span><span class="sxs-lookup"><span data-stu-id="c28e5-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="c28e5-153">Värdena för den nya tuppeln-typen är tuples som bildas av sekvenser av värden från varje typ i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="c28e5-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="c28e5-154">`(3, false)` är till exempel en tupel vars typ är Tuple-typen `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="c28e5-155">Det går att skapa matriser av tupler, tupler av matriser, tupler av under tupler osv.</span><span class="sxs-lookup"><span data-stu-id="c28e5-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="c28e5-156">Från och med Q # 0,3 är `Unit` namnet på den tomma tuplens *typ* . `()` används för det tomma tuple- *värdet*.</span><span class="sxs-lookup"><span data-stu-id="c28e5-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="c28e5-157">Tupel-instanser är oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="c28e5-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="c28e5-158">Q # innehåller ingen mekanism för att ändra innehållet i en tupel när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="c28e5-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="c28e5-159">Tupler är ett kraftfullt koncept som används i Q # för att samla in värden i ett enda värde, vilket gör det enklare att skicka dem till varandra.</span><span class="sxs-lookup"><span data-stu-id="c28e5-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="c28e5-160">I synnerhet kan vi, om du använder tupel notation, uttrycka att varje åtgärd och anrop bara tar exakt en indata och returnerar exakt ett resultat.</span><span class="sxs-lookup"><span data-stu-id="c28e5-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="c28e5-161">Jämförelse av singleton-tupel</span><span class="sxs-lookup"><span data-stu-id="c28e5-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="c28e5-162">Det går att skapa en singleton-tupel (Single-element), `('T1)`, till exempel `(5)` eller `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="c28e5-163">Q # behandlar dock en singleton-tupel som är helt likvärdig med värdet för den omslutna typen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="c28e5-164">Det innebär att det inte finns någon skillnad mellan `5` och `(5)`, eller mellan `5` och `(((5)))`, eller mellan `(5, (6))` och `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="c28e5-165">Den här motsvarigheten gäller för alla-syfte, inklusive tilldelning och uttryck.</span><span class="sxs-lookup"><span data-stu-id="c28e5-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="c28e5-166">Det är bara att skriva `(5)+3` som ska skriva `5+3`, och båda uttrycken kommer att utvärderas till `8`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="c28e5-167">Det innebär särskilt att en åtgärd eller funktion vars typ av tupel eller utgående tuple har ett fält kan betraktas som ett enda argument eller returnerar ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="c28e5-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="c28e5-168">Vi refererar till denna egenskap som _likhet med singleton-tupel_.</span><span class="sxs-lookup"><span data-stu-id="c28e5-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="c28e5-169">Användardefinierade typer</span><span class="sxs-lookup"><span data-stu-id="c28e5-169">User-Defined Types</span></span>

<span data-ttu-id="c28e5-170">En Q #-fil kan definiera en ny namngiven typ som innehåller ett enda värde av juridisk typ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="c28e5-171">För valfri tupel-typ `T`kan vi deklarera en ny användardefinierad typ som är en undertyp till `T` med `newtype`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="c28e5-172">I @"microsoft.quantum.canon"-namnrymden definieras komplexa tal som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="c28e5-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="c28e5-173">Den här instruktionen skapar en ny typ med två anonyma objekt av typen `Double`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="c28e5-174">Förutom anonyma objekt har användardefinierade typer även stöd för namngivna objekt från och med Q # version 0,7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c28e5-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="c28e5-175">Vi kan till exempel ha namngett objekten till objekt `Re` för det dubbla som representerar den verkliga delen av ett komplext tal och `Im` för den imaginära delen:</span><span class="sxs-lookup"><span data-stu-id="c28e5-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="c28e5-176">Att namnge ett objekt i en användardefinierad typ innebär inte att alla objekt måste vara namngivna – en kombination av namngivna och ej namngivna objekt stöds.</span><span class="sxs-lookup"><span data-stu-id="c28e5-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="c28e5-177">Dessutom kan inre objekt namnges.</span><span class="sxs-lookup"><span data-stu-id="c28e5-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="c28e5-178">Typen `Nested` som definieras nedan har exempelvis en underliggande typ `(Double, (Int, String))`, varav bara objektet av typen `Int` har namngetts och alla andra objekt är anonyma.</span><span class="sxs-lookup"><span data-stu-id="c28e5-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="c28e5-179">Namngivna objekt har fördelen att de kan nås direkt via åtkomst operatören `::`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="c28e5-180">För att få åtkomst till anonyma objekt, måste det omslutna värdet först extraheras med postfix-operatören `!`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="c28e5-181">Med operatorn "unwrap" `!`kan du extrahera värdet som finns i en användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="c28e5-182">Typen av "unwrap"-uttryck är den underliggande typen av användardefinierad typ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="c28e5-183">Unwrap-operatorn omger ett exakt rad brytnings lager.</span><span class="sxs-lookup"><span data-stu-id="c28e5-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="c28e5-184">Flera unwrap-operatorer kan användas för att få åtkomst till ett multiplicering-figursatt värde.</span><span class="sxs-lookup"><span data-stu-id="c28e5-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="c28e5-185">Exempel:</span><span class="sxs-lookup"><span data-stu-id="c28e5-185">For instance:</span></span>

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

<span data-ttu-id="c28e5-186">Ta en titt på avsnittet om att [packa upp uttryck](xref:microsoft.quantum.language.expressions#unwrap-expressions) och [operatorer prioritet](xref:microsoft.quantum.language.expressions#operator-precedence) för mer information.</span><span class="sxs-lookup"><span data-stu-id="c28e5-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="c28e5-187">Värdena för en användardefinierad typ kan skapas genom att anropa motsvarande typ-konstruktor:</span><span class="sxs-lookup"><span data-stu-id="c28e5-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="c28e5-188">Du kan också skapa nya värden från befintliga med hjälp av [Kopiera-och-uppdatera-uttryck](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="c28e5-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="c28e5-189">Precis som för matriser kopierar sådana uttryck alla objekt värden för det ursprungliga uttrycket, med undantag för de angivna namngivna objekten.</span><span class="sxs-lookup"><span data-stu-id="c28e5-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="c28e5-190">För dessa värden anges de som definierats till höger i uttrycket.</span><span class="sxs-lookup"><span data-stu-id="c28e5-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="c28e5-191">Andra språk konstruktioner, t. ex. [uppdaterings-och omtilldelnings instruktioner](xref:microsoft.quantum.language.statements#update-and-reassign-statement), som är tillgängliga för mat ris objekt finns även för namngivna objekt i användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="c28e5-192">Användardefinierade typer kan användas var som helst av andra typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="c28e5-193">I synnerhet är det möjligt att definiera en matris av en användardefinierad typ och för att inkludera en användardefinierad typ som ett element av en tupel-typ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="c28e5-194">Det går inte att skapa rekursiva typ strukturer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="c28e5-195">Det vill säga den typ som definierar en användardefinierad typ får inte vara en tuple-typ som innehåller ett element av den användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="c28e5-196">I allmänhet kan användardefinierade typer inte ha cykliska beroenden på varandra, så följande uppsättning typ definitioner skulle vara ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="c28e5-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="c28e5-197">Förutom att tillhandahålla korta alias för potentiellt komplicerade tuple-typer, är en stor fördel med att definiera sådana typer att de kan dokumentera syftet med ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="c28e5-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="c28e5-198">Om du återgår till exemplet på `Complex`kan en av dem också ha definierat 2D polär-koordinater som en användardefinierad typ:</span><span class="sxs-lookup"><span data-stu-id="c28e5-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="c28e5-199">Även om både `Complex` och `Polar` har en underliggande typ `(Double, Double)`är de två typerna helt inkompatibla i Q #, vilket minimerar risken för att oavsiktligt anropa en komplex matematik funktion med polära koordinater och vice versa.</span><span class="sxs-lookup"><span data-stu-id="c28e5-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="c28e5-200">På så sätt har användardefinierade typer en liknande roll som poster i F# till exempel.</span><span class="sxs-lookup"><span data-stu-id="c28e5-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="c28e5-201">Åtgärds-och funktions typer</span><span class="sxs-lookup"><span data-stu-id="c28e5-201">Operation and Function Types</span></span>

<span data-ttu-id="c28e5-202">En Q #- _åtgärd_ är en Quantum-underrutin.</span><span class="sxs-lookup"><span data-stu-id="c28e5-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="c28e5-203">Det vill säga att det är en rutin som kan anropas och som innehåller Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c28e5-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="c28e5-204">_Funktionen_ Q # är en klassisk underrutin som används i en Quantum-algoritm.</span><span class="sxs-lookup"><span data-stu-id="c28e5-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="c28e5-205">Den kan innehålla en klassisk kod men inga Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c28e5-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="c28e5-206">Mer specifikt kan funktioner inte allokera eller låna qubits, och de kan inte anropa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c28e5-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="c28e5-207">Det går dock att skicka dem eller qubits för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="c28e5-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="c28e5-208">Funktioner är därför helt deterministiska i den mening som anropar dem med samma argument kommer alltid att ge samma resultat.</span><span class="sxs-lookup"><span data-stu-id="c28e5-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="c28e5-209">Tillsammans kallas åtgärder och funktioner _callables_.</span><span class="sxs-lookup"><span data-stu-id="c28e5-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="c28e5-210">Du kan se några [exempel](#examples) på dessa nedan.</span><span class="sxs-lookup"><span data-stu-id="c28e5-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="c28e5-211">Alla Q # callables anses ta ett enda värde som indata och returnera ett enda värde som utdata.</span><span class="sxs-lookup"><span data-stu-id="c28e5-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="c28e5-212">Både in-och utdata-värden kan vara tupler.</span><span class="sxs-lookup"><span data-stu-id="c28e5-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="c28e5-213">Callables som inte returnerar resultat `Unit`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="c28e5-214">Callables som inte har något inmatade tar den tomma tuppeln som inmatad.</span><span class="sxs-lookup"><span data-stu-id="c28e5-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="c28e5-215">Den grundläggande typen för anrop är skriven som `('Tinput => 'Tresult)` eller `('Tinput -> 'Tresult)`, där både `'Tinput` och `'Tresult` är typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="c28e5-216">Det första formuläret, med `=>`, används för åtgärder. det andra formuläret, med `->`, för functions.</span><span class="sxs-lookup"><span data-stu-id="c28e5-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="c28e5-217">`((Qubit, Pauli) => Result)` representerar till exempel signaturen för en möjlig mätnings åtgärd med en qubit.</span><span class="sxs-lookup"><span data-stu-id="c28e5-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="c28e5-218">Funktions typer anges fullständigt av signaturen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="c28e5-219">En funktion som beräknar sinus för en vinkel skulle till exempel ha typen `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="c28e5-220">Åtgärder – men inte Functions – har vissa ytterligare _Egenskaper_ som uttrycks som en del av åtgärds typen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="c28e5-221">Dessa egenskaper innehåller information om vad functors åtgärden stöder.</span><span class="sxs-lookup"><span data-stu-id="c28e5-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="c28e5-222">Functors är meta-åtgärder som genererar en specialisering av en bas åtgärd. Se [Functors](#functors)nedan.</span><span class="sxs-lookup"><span data-stu-id="c28e5-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="c28e5-223">Åtgärds typer anges av deras typ av Indatatyp, Utdatatyp och deras egenskaper.</span><span class="sxs-lookup"><span data-stu-id="c28e5-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="c28e5-224">För att kunna kräva stöd för `Controlled` och/eller `Adjoint` Functor i en åtgärds typ, måste vi lägga till en anteckning som anger motsvarande egenskaper.</span><span class="sxs-lookup"><span data-stu-id="c28e5-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="c28e5-225">En antecknings `is Ctl` till exempel anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="c28e5-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="c28e5-226">Om vi vill kräva att en åtgärd av den typen stöder både `Adjoint` och `Controlled` Functor kan vi uttrycka detta som `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="c28e5-227">De använda åtgärds egenskaperna `Adj` och `Ctl` strikta tal är två fördefinierade uppsättningar med etiketter, där varje etikett anger en viss åtgärds egenskaper som t. ex. stöd för en viss Functor.</span><span class="sxs-lookup"><span data-stu-id="c28e5-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="c28e5-228">Därför används `+` för att ange union av dessa två uppsättningar och `*` används för att ange skärnings punkten – d.v.s. de etiketter som är gemensamma för båda uppsättningarna.</span><span class="sxs-lookup"><span data-stu-id="c28e5-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="c28e5-229">Till exempel har Pauli `X`-åtgärden typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="c28e5-230">En åtgärds typ som inte har stöd för någon functors anges av enbart indata-och Utdatatyp, utan ytterligare anteckning.</span><span class="sxs-lookup"><span data-stu-id="c28e5-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="c28e5-231">Typ-parameter funktioner och åtgärder</span><span class="sxs-lookup"><span data-stu-id="c28e5-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="c28e5-232">Typer som kan anropas kan innehålla typ parametrar.</span><span class="sxs-lookup"><span data-stu-id="c28e5-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="c28e5-233">Typ parametrar anges med en symbol som föregås av ett enkelt citat tecken. till exempel är `'A` en juridisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="c28e5-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="c28e5-234">En typ parameter kan visas mer än en gång i en enda signatur.</span><span class="sxs-lookup"><span data-stu-id="c28e5-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="c28e5-235">En funktion som till exempel tillämpar en annan funktion på varje element i en matris och returnerar de insamlade resultaten har signaturen `(('A[], 'A->'A) -> 'A[])`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="c28e5-236">På samma sätt kan en funktion som returnerar sammansättningen av två åtgärder ha signatur `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="c28e5-237">När du anropar en typ-parameter anrops bara, måste alla argument som har samma typ parameter vara av samma typ.</span><span class="sxs-lookup"><span data-stu-id="c28e5-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="c28e5-238">Q # innehåller ingen mekanism för att begränsa de möjliga typer som kan ersättas av en typ parameter.</span><span class="sxs-lookup"><span data-stu-id="c28e5-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="c28e5-239">Skriv kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="c28e5-239">Type Compatibility</span></span>

<span data-ttu-id="c28e5-240">En åtgärd med ytterligare functors som stöds kan användas överallt där en åtgärd har färre functors men samma signatur förväntas.</span><span class="sxs-lookup"><span data-stu-id="c28e5-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="c28e5-241">Till exempel kan en åtgärd av typen `(Qubit => Unit is Adj)` användas överallt där en åtgärd av typen `(Qubit => Unit)` förväntas.</span><span class="sxs-lookup"><span data-stu-id="c28e5-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="c28e5-242">Q # är samvariant med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med en typ som kan anropas med samma Indatatyp och en resultat typ som `'A` är kompatibel med.</span><span class="sxs-lookup"><span data-stu-id="c28e5-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="c28e5-243">Q # är contravariant med avseende på indatatyper: ett anrop som tar en typ `'A` som inmatare är kompatibel med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="c28e5-244">Det innebär att man får följande definitioner:</span><span class="sxs-lookup"><span data-stu-id="c28e5-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="c28e5-245">följande är sant:</span><span class="sxs-lookup"><span data-stu-id="c28e5-245">the following are true:</span></span>

- <span data-ttu-id="c28e5-246">Åtgärden `ConjugateInvertibleWith` kan anropas med ett `inner` argument för antingen `Invertible` eller `Unitary`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="c28e5-247">Åtgärden `ConjugateUnitaryWith` kan anropas med ett `inner` argument av `Unitary`, men inte `Invertible`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="c28e5-248">Ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` kan returneras från `ConjugateInvertibleWith`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c28e5-249">I Q # 0,3 införs en betydande skillnad i beteendet för användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="c28e5-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="c28e5-250">Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.</span><span class="sxs-lookup"><span data-stu-id="c28e5-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="c28e5-251">Det innebär att ett värde för en användardefinierad typ inte kan användas om ett värde av den underliggande typen förväntas.</span><span class="sxs-lookup"><span data-stu-id="c28e5-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="c28e5-252">Functors</span><span class="sxs-lookup"><span data-stu-id="c28e5-252">Functors</span></span>

<span data-ttu-id="c28e5-253">En Functor i Q # är en fabrik som definierar en ny åtgärd från en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c28e5-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="c28e5-254">Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="c28e5-255">Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå.</span><span class="sxs-lookup"><span data-stu-id="c28e5-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="c28e5-256">Functors har ingen representation i Q #-typ systemet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="c28e5-257">Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument.</span><span class="sxs-lookup"><span data-stu-id="c28e5-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="c28e5-258">En Functor används genom att tillämpa den på en åtgärd och returnera en ny åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c28e5-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="c28e5-259">Till exempel skrivs åtgärden som resulterar i att använda `Adjoint`-Functor till `Y`-åtgärden som `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="c28e5-260">Den nya åtgärden kan sedan anropas som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="c28e5-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="c28e5-261">Därför använder `Adjoint Y(q1)` det intilliggande Functor till åtgärden `Y` för att generera en ny åtgärd och tillämpar den nya åtgärden på `q1`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="c28e5-262">På samma sätt tillämpar `Controlled X(controls, target)` kontrollerade Functor i `X`-åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden på `controls` och `target`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="c28e5-263">De två standard functors i Q # är `Adjoint` och `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="c28e5-264">Angränsande</span><span class="sxs-lookup"><span data-stu-id="c28e5-264">Adjoint</span></span>

<span data-ttu-id="c28e5-265">I Quantum Computing är det angränsande av en åtgärd den komplexa konjugatet för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="c28e5-266">För åtgärder som implementerar en enhetlig operatör är det intilliggande inversen till åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="c28e5-267">För en enkel åtgärd som bara anropar en sekvens med andra enhetliga åtgärder på en uppsättning qubits, kan det intilliggande värdet beräknas genom att använda angränsande åtgärder på samma qubits i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="c28e5-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="c28e5-268">Med ett åtgärds uttryck kan ett nytt åtgärds uttryck skapas med hjälp av `Adjoint` Functor.</span><span class="sxs-lookup"><span data-stu-id="c28e5-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="c28e5-269">`Adjoint QFT` anger till exempel den angränsande av `QFT` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="c28e5-270">Den nya åtgärden har samma signatur och typ som bas åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c28e5-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="c28e5-271">I synnerhet tillåter den nya åtgärden också `Adjoint`, och kommer att tillåta `Controlled` om och endast om bas åtgärden har utförts.</span><span class="sxs-lookup"><span data-stu-id="c28e5-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="c28e5-272">Det intilliggande Functor är en egen invertering; det vill säga `Adjoint Adjoint Op` alltid är detsamma som `Op`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="c28e5-273">Styr</span><span class="sxs-lookup"><span data-stu-id="c28e5-273">Controlled</span></span>

<span data-ttu-id="c28e5-274">Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="c28e5-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="c28e5-275">Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.</span><span class="sxs-lookup"><span data-stu-id="c28e5-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="c28e5-276">Därmed används kontrollerade åtgärder ofta för att generera entanglement.</span><span class="sxs-lookup"><span data-stu-id="c28e5-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="c28e5-277">I Q # tar kontrollerade versioner alltid en matris med Control-qubits, och det angivna läget är alltid för alla kontroll qubits att vara i`PauliZ`beräknings `One`s status $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="c28e5-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="c28e5-278">Kontroll som bygger på andra tillstånd kan uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="c28e5-279">Om du till exempel använder en `X`-åtgärd för en kontroll qubit före och efter en kontrollerad åtgärd, kommer åtgärden att kontrol lera `Zero` tillstånd ($ \ket{0}$) för qubit; att tillämpa en `H`-åtgärd innan och efter styrs av `PauliX` `One` tillstånd, det vill säga 1 eigenvalue av Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ i stället för `PauliZ` `One`-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="c28e5-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="c28e5-280">Med ett åtgärds uttryck kan ett nytt åtgärds uttryck skapas med hjälp av `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="c28e5-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="c28e5-281">Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="c28e5-282">Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="c28e5-283">Den nya åtgärden stöder `Controlled`och har stöd för `Adjoint` om och bara om den ursprungliga åtgärden utfördes.</span><span class="sxs-lookup"><span data-stu-id="c28e5-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="c28e5-284">Om den ursprungliga åtgärden bara tog ett enda argument, kommer singleton-tupel att visas här.</span><span class="sxs-lookup"><span data-stu-id="c28e5-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="c28e5-285">`Controlled X` är till exempel den kontrollerade versionen av `X` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="c28e5-286">`X` har typen `(Qubit => Unit is Adj + Ctl)`, så `Controlled X` har typen `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; på grund av singleton tuple-motsvarighet är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="c28e5-287">Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.</span><span class="sxs-lookup"><span data-stu-id="c28e5-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="c28e5-288">`Controlled Rz` är till exempel den kontrollerade versionen av `Rz` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="c28e5-289">`Rz` har typen `((Double, Qubit) => Unit is Adj + Ctl)`, så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="c28e5-290">Därför är `Controlled Rz(controls, (0.1, target))` ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="c28e5-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="c28e5-291">I ett annat exempel kan `CNOT(control, target)` implementeras som `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="c28e5-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="c28e5-292">Om ett mål ska styras av 2 Control qubits (CCNOT) kan vi använda `Controlled X([control1, control2], target)` instruktion.</span><span class="sxs-lookup"><span data-stu-id="c28e5-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="c28e5-293">Exempel</span><span class="sxs-lookup"><span data-stu-id="c28e5-293">Examples</span></span>

<span data-ttu-id="c28e5-294">Det här exemplet på en Q #-åtgärd kommer från [mått](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) exemplet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="c28e5-295">Inom åtgärder kan vi allokera qubits och använda Quantum-åtgärder på dessa qubits, till exempel `H` och `X`:</span><span class="sxs-lookup"><span data-stu-id="c28e5-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="c28e5-296">Det här exemplet på en funktion kommer från [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) -exemplet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="c28e5-297">Den innehåller en helt klassisk kod.</span><span class="sxs-lookup"><span data-stu-id="c28e5-297">It contains purely classical code.</span></span> <span data-ttu-id="c28e5-298">Du kan se att, till skillnad från exemplet ovan, inga qubits har tilldelats och inga Quantum-åtgärder används.</span><span class="sxs-lookup"><span data-stu-id="c28e5-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="c28e5-299">Det är också möjligt att en funktion skickas qubits för bearbetning, som i det här exemplet från [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) -exemplet.</span><span class="sxs-lookup"><span data-stu-id="c28e5-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="c28e5-300">Qubits skickas till funktionen och används för bearbetning, men vid ingen tidpunkt modifieras qubit-tillstånden.</span><span class="sxs-lookup"><span data-stu-id="c28e5-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
