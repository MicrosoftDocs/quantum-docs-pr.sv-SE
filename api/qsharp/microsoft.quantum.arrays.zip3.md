---
uid: Microsoft.Quantum.Arrays.Zip3
title: Funktionen Zip3
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729918"
---
# <a name="zip3-function"></a><span data-ttu-id="408f2-102">Funktionen Zip3</span><span class="sxs-lookup"><span data-stu-id="408f2-102">Zip3 function</span></span>

<span data-ttu-id="408f2-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="408f2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="408f2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="408f2-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="408f2-105">Zip3 är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="408f2-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="408f2-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped3> i stället.</span><span class="sxs-lookup"><span data-stu-id="408f2-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="408f2-107">Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="408f2-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="408f2-108">Indata</span><span class="sxs-lookup"><span data-stu-id="408f2-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="408f2-109">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="408f2-109">first : 'T1[]</span></span>

<span data-ttu-id="408f2-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="408f2-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="408f2-111">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="408f2-111">second : 'T2[]</span></span>

<span data-ttu-id="408f2-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="408f2-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="408f2-113">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="408f2-113">third : 'T3[]</span></span>

<span data-ttu-id="408f2-114">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="408f2-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="408f2-115">Utdata: (t. ex. 1, inte 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="408f2-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="408f2-116">En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="408f2-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="408f2-117">Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="408f2-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="408f2-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="408f2-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="408f2-119">T 1</span><span class="sxs-lookup"><span data-stu-id="408f2-119">'T1</span></span>

<span data-ttu-id="408f2-120">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="408f2-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="408f2-121">Inte 2</span><span class="sxs-lookup"><span data-stu-id="408f2-121">'T2</span></span>

<span data-ttu-id="408f2-122">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="408f2-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="408f2-123">Inte 3</span><span class="sxs-lookup"><span data-stu-id="408f2-123">'T3</span></span>

<span data-ttu-id="408f2-124">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="408f2-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="408f2-125">Se även</span><span class="sxs-lookup"><span data-stu-id="408f2-125">See Also</span></span>

- [<span data-ttu-id="408f2-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="408f2-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="408f2-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="408f2-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)