---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorterad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730027"
---
# <a name="sorted-function"></a><span data-ttu-id="8ab03-102">Sorterad funktion</span><span class="sxs-lookup"><span data-stu-id="8ab03-102">Sorted function</span></span>

<span data-ttu-id="8ab03-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ab03-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ab03-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ab03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ab03-105">Utifrån en matris returnerar elementen i den matrisen sorterad efter en specifik jämförelse funktion.</span><span class="sxs-lookup"><span data-stu-id="8ab03-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8ab03-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8ab03-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="8ab03-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8ab03-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8ab03-108">En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="8ab03-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="8ab03-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="8ab03-109">array : 'T[]</span></span>

<span data-ttu-id="8ab03-110">Matrisen som ska sorteras.</span><span class="sxs-lookup"><span data-stu-id="8ab03-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="8ab03-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="8ab03-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ab03-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8ab03-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ab03-113">Inte</span><span class="sxs-lookup"><span data-stu-id="8ab03-113">'T</span></span>

<span data-ttu-id="8ab03-114">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="8ab03-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ab03-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8ab03-115">Remarks</span></span>

<span data-ttu-id="8ab03-116">Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas.</span><span class="sxs-lookup"><span data-stu-id="8ab03-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="8ab03-117">Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.</span><span class="sxs-lookup"><span data-stu-id="8ab03-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="8ab03-118">Eftersom det här är en funktion är resultatet helt Determinstic, även om två element anses vara lika under `comparison` ; det vill säga när `comparison(a, b)` och `comparison(b, a)` är båda `true` .</span><span class="sxs-lookup"><span data-stu-id="8ab03-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="8ab03-119">I synnerhet är sorteringen som utförs av den här funktionen säkerställd att vara stabil, så att om två element `a` och `b` inträffar i den ordningen i `array` och betraktas som likvärdiga `comparison` , `a` visas även före `b` i utdata.</span><span class="sxs-lookup"><span data-stu-id="8ab03-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="8ab03-120">Exempel:</span><span class="sxs-lookup"><span data-stu-id="8ab03-120">For example:</span></span>

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