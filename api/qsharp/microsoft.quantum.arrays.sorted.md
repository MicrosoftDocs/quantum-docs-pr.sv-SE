---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorterad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845451"
---
# <a name="sorted-function"></a><span data-ttu-id="ae2b9-102">Sorterad funktion</span><span class="sxs-lookup"><span data-stu-id="ae2b9-102">Sorted function</span></span>

<span data-ttu-id="ae2b9-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ae2b9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ae2b9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae2b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae2b9-105">Utifrån en matris returnerar elementen i den matrisen sorterad efter en specifik jämförelse funktion.</span><span class="sxs-lookup"><span data-stu-id="ae2b9-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ae2b9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ae2b9-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="ae2b9-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ae2b9-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ae2b9-108">En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="ae2b9-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="ae2b9-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="ae2b9-109">array : 'T[]</span></span>

<span data-ttu-id="ae2b9-110">Matrisen som ska sorteras.</span><span class="sxs-lookup"><span data-stu-id="ae2b9-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="ae2b9-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="ae2b9-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ae2b9-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ae2b9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae2b9-113">Inte</span><span class="sxs-lookup"><span data-stu-id="ae2b9-113">'T</span></span>

<span data-ttu-id="ae2b9-114">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="ae2b9-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="ae2b9-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="ae2b9-115">Example</span></span>

<span data-ttu-id="ae2b9-116">Följande kodfragment sorterar en matris med heltal som ska ske i stigande ordning:</span><span class="sxs-lookup"><span data-stu-id="ae2b9-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="ae2b9-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ae2b9-117">Remarks</span></span>

<span data-ttu-id="ae2b9-118">Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas.</span><span class="sxs-lookup"><span data-stu-id="ae2b9-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="ae2b9-119">Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.</span><span class="sxs-lookup"><span data-stu-id="ae2b9-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="ae2b9-120">Eftersom det här är en funktion är resultatet helt Determinstic, även om två element anses vara lika under `comparison` ; det vill säga när `comparison(a, b)` och `comparison(b, a)` är båda `true` .</span><span class="sxs-lookup"><span data-stu-id="ae2b9-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="ae2b9-121">I synnerhet är sorteringen som utförs av den här funktionen säkerställd att vara stabil, så att om två element `a` och `b` inträffar i den ordningen i `array` och betraktas som likvärdiga `comparison` , `a` visas även före `b` i utdata.</span><span class="sxs-lookup"><span data-stu-id="ae2b9-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="ae2b9-122">Exempel:</span><span class="sxs-lookup"><span data-stu-id="ae2b9-122">For example:</span></span>

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```