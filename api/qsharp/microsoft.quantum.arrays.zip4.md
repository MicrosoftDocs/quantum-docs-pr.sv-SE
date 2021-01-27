---
uid: Microsoft.Quantum.Arrays.Zip4
title: Funktionen Zip4
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850888"
---
# <a name="zip4-function"></a><span data-ttu-id="953a5-102">Funktionen Zip4</span><span class="sxs-lookup"><span data-stu-id="953a5-102">Zip4 function</span></span>

<span data-ttu-id="953a5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="953a5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="953a5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="953a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="953a5-105">Zip4 är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="953a5-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="953a5-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped4> i stället.</span><span class="sxs-lookup"><span data-stu-id="953a5-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="953a5-107">Med fyra matriser returnerar en ny matris med 4-tupler, så att varje 4-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="953a5-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="953a5-108">Indata</span><span class="sxs-lookup"><span data-stu-id="953a5-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="953a5-109">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="953a5-109">first : 'T1[]</span></span>

<span data-ttu-id="953a5-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="953a5-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="953a5-111">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="953a5-111">second : 'T2[]</span></span>

<span data-ttu-id="953a5-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="953a5-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="953a5-113">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="953a5-113">third : 'T3[]</span></span>

<span data-ttu-id="953a5-114">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="953a5-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="953a5-115">fjärde: inte 4 []</span><span class="sxs-lookup"><span data-stu-id="953a5-115">fourth : 'T4[]</span></span>

<span data-ttu-id="953a5-116">En matris som innehåller värden för det fjärde elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="953a5-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="953a5-117">Utdata: (t. ex. 1, inte den 3, inte 4) []</span><span class="sxs-lookup"><span data-stu-id="953a5-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="953a5-118">En matris som innehåller 4 tupler av formuläret `(first[idx], second[idx], third[idx], fourth[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="953a5-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="953a5-119">Om de fyra matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="953a5-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="953a5-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="953a5-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="953a5-121">T 1</span><span class="sxs-lookup"><span data-stu-id="953a5-121">'T1</span></span>

<span data-ttu-id="953a5-122">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="953a5-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="953a5-123">Inte 2</span><span class="sxs-lookup"><span data-stu-id="953a5-123">'T2</span></span>

<span data-ttu-id="953a5-124">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="953a5-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="953a5-125">Inte 3</span><span class="sxs-lookup"><span data-stu-id="953a5-125">'T3</span></span>

<span data-ttu-id="953a5-126">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="953a5-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="953a5-127">Inte 4</span><span class="sxs-lookup"><span data-stu-id="953a5-127">'T4</span></span>

<span data-ttu-id="953a5-128">Typ av fjärde mat ris element.</span><span class="sxs-lookup"><span data-stu-id="953a5-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="953a5-129">Se även</span><span class="sxs-lookup"><span data-stu-id="953a5-129">See Also</span></span>

- [<span data-ttu-id="953a5-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="953a5-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="953a5-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="953a5-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)