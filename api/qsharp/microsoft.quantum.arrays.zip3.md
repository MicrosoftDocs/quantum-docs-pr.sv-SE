---
uid: Microsoft.Quantum.Arrays.Zip3
title: Funktionen Zip3
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219829"
---
# <a name="zip3-function"></a><span data-ttu-id="b0b3a-102">Funktionen Zip3</span><span class="sxs-lookup"><span data-stu-id="b0b3a-102">Zip3 function</span></span>

<span data-ttu-id="b0b3a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0b3a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0b3a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0b3a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="b0b3a-105">Zip3 är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="b0b3a-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped3> i stället.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="b0b3a-107">Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b0b3a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="b0b3a-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b0b3a-109">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="b0b3a-109">first : 'T1[]</span></span>

<span data-ttu-id="b0b3a-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b0b3a-111">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="b0b3a-111">second : 'T2[]</span></span>

<span data-ttu-id="b0b3a-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b0b3a-113">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="b0b3a-113">third : 'T3[]</span></span>

<span data-ttu-id="b0b3a-114">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b0b3a-115">Utdata: (t. ex. 1, inte 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="b0b3a-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b0b3a-116">En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="b0b3a-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b0b3a-117">Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0b3a-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b0b3a-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b0b3a-119">T 1</span><span class="sxs-lookup"><span data-stu-id="b0b3a-119">'T1</span></span>

<span data-ttu-id="b0b3a-120">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b0b3a-121">Inte 2</span><span class="sxs-lookup"><span data-stu-id="b0b3a-121">'T2</span></span>

<span data-ttu-id="b0b3a-122">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b0b3a-123">Inte 3</span><span class="sxs-lookup"><span data-stu-id="b0b3a-123">'T3</span></span>

<span data-ttu-id="b0b3a-124">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="b0b3a-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0b3a-125">Se även</span><span class="sxs-lookup"><span data-stu-id="b0b3a-125">See Also</span></span>

- [<span data-ttu-id="b0b3a-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="b0b3a-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="b0b3a-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="b0b3a-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)