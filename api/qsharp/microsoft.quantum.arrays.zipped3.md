---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Funktionen Zipped3
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842182"
---
# <a name="zipped3-function"></a><span data-ttu-id="3f069-102">Funktionen Zipped3</span><span class="sxs-lookup"><span data-stu-id="3f069-102">Zipped3 function</span></span>

<span data-ttu-id="3f069-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3f069-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3f069-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f069-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f069-105">Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="3f069-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="3f069-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3f069-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="3f069-107">första: ' t 1 []</span><span class="sxs-lookup"><span data-stu-id="3f069-107">first : 'T1[]</span></span>

<span data-ttu-id="3f069-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="3f069-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="3f069-109">sekund: inte 2 []</span><span class="sxs-lookup"><span data-stu-id="3f069-109">second : 'T2[]</span></span>

<span data-ttu-id="3f069-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="3f069-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="3f069-111">tredje: inte 3 []</span><span class="sxs-lookup"><span data-stu-id="3f069-111">third : 'T3[]</span></span>

<span data-ttu-id="3f069-112">En matris som innehåller värden för det tredje elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="3f069-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="3f069-113">Utdata: (t. ex. 1, inte 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="3f069-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="3f069-114">En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="3f069-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="3f069-115">Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="3f069-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3f069-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3f069-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="3f069-117">T 1</span><span class="sxs-lookup"><span data-stu-id="3f069-117">'T1</span></span>

<span data-ttu-id="3f069-118">Typen för de första mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="3f069-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="3f069-119">Inte 2</span><span class="sxs-lookup"><span data-stu-id="3f069-119">'T2</span></span>

<span data-ttu-id="3f069-120">Typ av andra mat ris element.</span><span class="sxs-lookup"><span data-stu-id="3f069-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="3f069-121">Inte 3</span><span class="sxs-lookup"><span data-stu-id="3f069-121">'T3</span></span>

<span data-ttu-id="3f069-122">Typen för de tredje mat ris elementen.</span><span class="sxs-lookup"><span data-stu-id="3f069-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f069-123">Se även</span><span class="sxs-lookup"><span data-stu-id="3f069-123">See Also</span></span>

- [<span data-ttu-id="3f069-124">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="3f069-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="3f069-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="3f069-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)