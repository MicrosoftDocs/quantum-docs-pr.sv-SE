---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorterad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220237"
---
# <a name="sorted-function"></a><span data-ttu-id="fde4b-102">Sorterad funktion</span><span class="sxs-lookup"><span data-stu-id="fde4b-102">Sorted function</span></span>

<span data-ttu-id="fde4b-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fde4b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fde4b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fde4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fde4b-105">Utifrån en matris returnerar elementen i den matrisen sorterad efter en specifik jämförelse funktion.</span><span class="sxs-lookup"><span data-stu-id="fde4b-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fde4b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fde4b-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="fde4b-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fde4b-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fde4b-108">En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="fde4b-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="fde4b-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="fde4b-109">array : 'T[]</span></span>

<span data-ttu-id="fde4b-110">Matrisen som ska sorteras.</span><span class="sxs-lookup"><span data-stu-id="fde4b-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="fde4b-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="fde4b-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fde4b-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fde4b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fde4b-113">Inte</span><span class="sxs-lookup"><span data-stu-id="fde4b-113">'T</span></span>

<span data-ttu-id="fde4b-114">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="fde4b-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fde4b-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="fde4b-115">Remarks</span></span>

<span data-ttu-id="fde4b-116">Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas.</span><span class="sxs-lookup"><span data-stu-id="fde4b-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="fde4b-117">Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.</span><span class="sxs-lookup"><span data-stu-id="fde4b-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="fde4b-118">Eftersom det här är en funktion är resultatet helt Determinstic, även om två element anses vara lika under `comparison` ; det vill säga när `comparison(a, b)` och `comparison(b, a)` är båda `true` .</span><span class="sxs-lookup"><span data-stu-id="fde4b-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="fde4b-119">I synnerhet är sorteringen som utförs av den här funktionen säkerställd att vara stabil, så att om två element `a` och `b` inträffar i den ordningen i `array` och betraktas som likvärdiga `comparison` , `a` visas även före `b` i utdata.</span><span class="sxs-lookup"><span data-stu-id="fde4b-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="fde4b-120">Exempel:</span><span class="sxs-lookup"><span data-stu-id="fde4b-120">For example:</span></span>

```Q#
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