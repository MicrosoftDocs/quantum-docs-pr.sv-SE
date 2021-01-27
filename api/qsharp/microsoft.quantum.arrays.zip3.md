---
uid: Microsoft.Quantum.Arrays.Zip3
title: Funktionen Zip3
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845359"
---
# <a name="zip3-function"></a><span data-ttu-id="7e1e6-102">Funktionen Zip3</span><span class="sxs-lookup"><span data-stu-id="7e1e6-102">Zip3 function</span></span>

<span data-ttu-id="7e1e6-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7e1e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7e1e6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e1e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7e1e6-105">Zip3 är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="7e1e6-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped3> i stället.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="7e1e6-107">Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="7e1e6-108">Indata</span><span class="sxs-lookup"><span data-stu-id="7e1e6-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="7e1e6-109">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="7e1e6-109">first : 'T1[]</span></span>

<span data-ttu-id="7e1e6-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="7e1e6-111">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="7e1e6-111">second : 'T2[]</span></span>

<span data-ttu-id="7e1e6-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="7e1e6-113">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="7e1e6-113">third : 'T3[]</span></span>

<span data-ttu-id="7e1e6-114">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="7e1e6-115">Utdata: (t. ex. 1, inte 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="7e1e6-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="7e1e6-116">En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="7e1e6-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="7e1e6-117">Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7e1e6-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7e1e6-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="7e1e6-119">T 1</span><span class="sxs-lookup"><span data-stu-id="7e1e6-119">'T1</span></span>

<span data-ttu-id="7e1e6-120">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="7e1e6-121">Inte 2</span><span class="sxs-lookup"><span data-stu-id="7e1e6-121">'T2</span></span>

<span data-ttu-id="7e1e6-122">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="7e1e6-123">Inte 3</span><span class="sxs-lookup"><span data-stu-id="7e1e6-123">'T3</span></span>

<span data-ttu-id="7e1e6-124">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="7e1e6-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e1e6-125">Se även</span><span class="sxs-lookup"><span data-stu-id="7e1e6-125">See Also</span></span>

- [<span data-ttu-id="7e1e6-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="7e1e6-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="7e1e6-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="7e1e6-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)