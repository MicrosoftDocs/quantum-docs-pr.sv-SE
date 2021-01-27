---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845341"
---
# <a name="zipped-function"></a><span data-ttu-id="afcea-102">Komprimerad funktion</span><span class="sxs-lookup"><span data-stu-id="afcea-102">Zipped function</span></span>

<span data-ttu-id="afcea-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afcea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afcea-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afcea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afcea-105">Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="afcea-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="afcea-106">Indata</span><span class="sxs-lookup"><span data-stu-id="afcea-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="afcea-107">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="afcea-107">left : 'T[]</span></span>

<span data-ttu-id="afcea-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="afcea-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="afcea-109">höger: U []</span><span class="sxs-lookup"><span data-stu-id="afcea-109">right : 'U[]</span></span>

<span data-ttu-id="afcea-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="afcea-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="afcea-111">Utdata: (t, U) []</span><span class="sxs-lookup"><span data-stu-id="afcea-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="afcea-112">En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="afcea-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="afcea-113">Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="afcea-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afcea-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="afcea-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afcea-115">Inte</span><span class="sxs-lookup"><span data-stu-id="afcea-115">'T</span></span>

<span data-ttu-id="afcea-116">Typ av vänster mat ris element.</span><span class="sxs-lookup"><span data-stu-id="afcea-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="afcea-117">' U</span><span class="sxs-lookup"><span data-stu-id="afcea-117">'U</span></span>

<span data-ttu-id="afcea-118">Typ av höger mat ris element.</span><span class="sxs-lookup"><span data-stu-id="afcea-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="afcea-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="afcea-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="afcea-120">Se även</span><span class="sxs-lookup"><span data-stu-id="afcea-120">See Also</span></span>

- [<span data-ttu-id="afcea-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="afcea-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="afcea-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="afcea-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="afcea-123">Microsoft. Quantum. arrayer. unzippad</span><span class="sxs-lookup"><span data-stu-id="afcea-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)