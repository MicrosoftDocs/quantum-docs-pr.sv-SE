---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219761"
---
# <a name="zipped-function"></a><span data-ttu-id="b114d-102">Komprimerad funktion</span><span class="sxs-lookup"><span data-stu-id="b114d-102">Zipped function</span></span>

<span data-ttu-id="b114d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b114d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b114d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b114d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b114d-105">Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="b114d-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="b114d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b114d-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="b114d-107">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="b114d-107">left : 'T[]</span></span>

<span data-ttu-id="b114d-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="b114d-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="b114d-109">höger: U []</span><span class="sxs-lookup"><span data-stu-id="b114d-109">right : 'U[]</span></span>

<span data-ttu-id="b114d-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="b114d-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="b114d-111">Utdata: (t, U) []</span><span class="sxs-lookup"><span data-stu-id="b114d-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="b114d-112">En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="b114d-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="b114d-113">Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="b114d-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b114d-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b114d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b114d-115">Inte</span><span class="sxs-lookup"><span data-stu-id="b114d-115">'T</span></span>

<span data-ttu-id="b114d-116">Typ av vänster mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b114d-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="b114d-117">' U</span><span class="sxs-lookup"><span data-stu-id="b114d-117">'U</span></span>

<span data-ttu-id="b114d-118">Typ av höger mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b114d-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b114d-119">Se även</span><span class="sxs-lookup"><span data-stu-id="b114d-119">See Also</span></span>

- [<span data-ttu-id="b114d-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="b114d-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="b114d-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="b114d-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="b114d-122">Microsoft. Quantum. arrayer. unzippad</span><span class="sxs-lookup"><span data-stu-id="b114d-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)