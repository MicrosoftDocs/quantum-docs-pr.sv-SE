---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729923"
---
# <a name="zip-function"></a><span data-ttu-id="9fda1-102">Zip-funktion</span><span class="sxs-lookup"><span data-stu-id="9fda1-102">Zip function</span></span>

<span data-ttu-id="9fda1-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9fda1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9fda1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fda1-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="9fda1-105">Zip är inaktuellt.</span><span class="sxs-lookup"><span data-stu-id="9fda1-105">Zip has been deprecated.</span></span> <span data-ttu-id="9fda1-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped> i stället.</span><span class="sxs-lookup"><span data-stu-id="9fda1-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="9fda1-107">Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="9fda1-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="9fda1-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9fda1-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="9fda1-109">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="9fda1-109">left : 'T[]</span></span>

<span data-ttu-id="9fda1-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="9fda1-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="9fda1-111">höger: U []</span><span class="sxs-lookup"><span data-stu-id="9fda1-111">right : 'U[]</span></span>

<span data-ttu-id="9fda1-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="9fda1-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="9fda1-113">Utdata: (t, U) []</span><span class="sxs-lookup"><span data-stu-id="9fda1-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="9fda1-114">En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="9fda1-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="9fda1-115">Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="9fda1-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fda1-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9fda1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fda1-117">Inte</span><span class="sxs-lookup"><span data-stu-id="9fda1-117">'T</span></span>

<span data-ttu-id="9fda1-118">Typ av vänster mat ris element.</span><span class="sxs-lookup"><span data-stu-id="9fda1-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="9fda1-119">' U</span><span class="sxs-lookup"><span data-stu-id="9fda1-119">'U</span></span>

<span data-ttu-id="9fda1-120">Typ av höger mat ris element.</span><span class="sxs-lookup"><span data-stu-id="9fda1-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fda1-121">Se även</span><span class="sxs-lookup"><span data-stu-id="9fda1-121">See Also</span></span>

- [<span data-ttu-id="9fda1-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="9fda1-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="9fda1-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="9fda1-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="9fda1-124">Microsoft. Quantum. arrayer. unzippad</span><span class="sxs-lookup"><span data-stu-id="9fda1-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)