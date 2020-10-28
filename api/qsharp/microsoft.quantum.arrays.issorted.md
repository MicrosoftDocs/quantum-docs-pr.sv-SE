---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funktionen IsSorted
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730171"
---
# <a name="issorted-function"></a><span data-ttu-id="18ad5-102">Funktionen IsSorted</span><span class="sxs-lookup"><span data-stu-id="18ad5-102">IsSorted function</span></span>

<span data-ttu-id="18ad5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="18ad5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="18ad5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18ad5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18ad5-105">Om matrisen anges returneras en matris som definieras av en viss jämförelse funktion.</span><span class="sxs-lookup"><span data-stu-id="18ad5-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="18ad5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="18ad5-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="18ad5-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="18ad5-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="18ad5-108">En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="18ad5-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="18ad5-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="18ad5-109">array : 'T[]</span></span>

<span data-ttu-id="18ad5-110">Den matris som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="18ad5-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="18ad5-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="18ad5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="18ad5-112">`true` om och endast om för varje par med element `a` och `b` `array` som inträffar i den ordningen, `comparison(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="18ad5-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="18ad5-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="18ad5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18ad5-114">Inte</span><span class="sxs-lookup"><span data-stu-id="18ad5-114">'T</span></span>

<span data-ttu-id="18ad5-115">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="18ad5-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18ad5-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="18ad5-116">Remarks</span></span>

<span data-ttu-id="18ad5-117">Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas.</span><span class="sxs-lookup"><span data-stu-id="18ad5-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="18ad5-118">Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.</span><span class="sxs-lookup"><span data-stu-id="18ad5-118">If this property does not hold, then the output of this function may be incorrect.</span></span>