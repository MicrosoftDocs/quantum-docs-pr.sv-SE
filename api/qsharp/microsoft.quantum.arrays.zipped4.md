---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Funktionen Zipped4
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219642"
---
# <a name="zipped4-function"></a><span data-ttu-id="6b5c5-102">Funktionen Zipped4</span><span class="sxs-lookup"><span data-stu-id="6b5c5-102">Zipped4 function</span></span>

<span data-ttu-id="6b5c5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6b5c5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6b5c5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b5c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b5c5-105">Med fyra matriser returnerar en ny matris med 4-tupler, så att varje 4-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="6b5c5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6b5c5-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="6b5c5-107">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="6b5c5-107">first : 'T1[]</span></span>

<span data-ttu-id="6b5c5-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="6b5c5-109">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="6b5c5-109">second : 'T2[]</span></span>

<span data-ttu-id="6b5c5-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="6b5c5-111">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="6b5c5-111">third : 'T3[]</span></span>

<span data-ttu-id="6b5c5-112">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="6b5c5-113">fjärde: inte 4 []</span><span class="sxs-lookup"><span data-stu-id="6b5c5-113">fourth : 'T4[]</span></span>

<span data-ttu-id="6b5c5-114">En matris som innehåller värden för det fjärde elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="6b5c5-115">Utdata: (t. ex. 1, inte den 3, inte 4) []</span><span class="sxs-lookup"><span data-stu-id="6b5c5-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="6b5c5-116">En matris som innehåller 4 tupler av formuläret `(first[idx], second[idx], third[idx], fourth[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="6b5c5-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="6b5c5-117">Om de fyra matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6b5c5-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6b5c5-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="6b5c5-119">T 1</span><span class="sxs-lookup"><span data-stu-id="6b5c5-119">'T1</span></span>

<span data-ttu-id="6b5c5-120">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="6b5c5-121">Inte 2</span><span class="sxs-lookup"><span data-stu-id="6b5c5-121">'T2</span></span>

<span data-ttu-id="6b5c5-122">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="6b5c5-123">Inte 3</span><span class="sxs-lookup"><span data-stu-id="6b5c5-123">'T3</span></span>

<span data-ttu-id="6b5c5-124">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="6b5c5-125">Inte 4</span><span class="sxs-lookup"><span data-stu-id="6b5c5-125">'T4</span></span>

<span data-ttu-id="6b5c5-126">Typ av fjärde mat ris element.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b5c5-127">Se även</span><span class="sxs-lookup"><span data-stu-id="6b5c5-127">See Also</span></span>

- [<span data-ttu-id="6b5c5-128">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="6b5c5-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="6b5c5-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="6b5c5-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)