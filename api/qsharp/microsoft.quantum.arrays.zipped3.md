---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Funktionen Zipped3
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729899"
---
# <a name="zipped3-function"></a><span data-ttu-id="100e5-102">Funktionen Zipped3</span><span class="sxs-lookup"><span data-stu-id="100e5-102">Zipped3 function</span></span>

<span data-ttu-id="100e5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="100e5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="100e5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="100e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="100e5-105">Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="100e5-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="100e5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="100e5-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="100e5-107">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="100e5-107">first : 'T1[]</span></span>

<span data-ttu-id="100e5-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="100e5-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="100e5-109">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="100e5-109">second : 'T2[]</span></span>

<span data-ttu-id="100e5-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="100e5-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="100e5-111">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="100e5-111">third : 'T3[]</span></span>

<span data-ttu-id="100e5-112">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="100e5-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="100e5-113">Utdata: (t. ex. 1, inte 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="100e5-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="100e5-114">En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="100e5-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="100e5-115">Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="100e5-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="100e5-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="100e5-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="100e5-117">T 1</span><span class="sxs-lookup"><span data-stu-id="100e5-117">'T1</span></span>

<span data-ttu-id="100e5-118">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="100e5-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="100e5-119">Inte 2</span><span class="sxs-lookup"><span data-stu-id="100e5-119">'T2</span></span>

<span data-ttu-id="100e5-120">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="100e5-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="100e5-121">Inte 3</span><span class="sxs-lookup"><span data-stu-id="100e5-121">'T3</span></span>

<span data-ttu-id="100e5-122">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="100e5-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="100e5-123">Se även</span><span class="sxs-lookup"><span data-stu-id="100e5-123">See Also</span></span>

- [<span data-ttu-id="100e5-124">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="100e5-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="100e5-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="100e5-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)