---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729910"
---
# <a name="zipped-function"></a><span data-ttu-id="93281-102">Komprimerad funktion</span><span class="sxs-lookup"><span data-stu-id="93281-102">Zipped function</span></span>

<span data-ttu-id="93281-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93281-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93281-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93281-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93281-105">Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="93281-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="93281-106">Indata</span><span class="sxs-lookup"><span data-stu-id="93281-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="93281-107">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="93281-107">left : 'T[]</span></span>

<span data-ttu-id="93281-108">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="93281-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="93281-109">höger: U []</span><span class="sxs-lookup"><span data-stu-id="93281-109">right : 'U[]</span></span>

<span data-ttu-id="93281-110">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="93281-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="93281-111">Utdata: (t, U) []</span><span class="sxs-lookup"><span data-stu-id="93281-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="93281-112">En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="93281-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="93281-113">Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="93281-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93281-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="93281-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93281-115">Inte</span><span class="sxs-lookup"><span data-stu-id="93281-115">'T</span></span>

<span data-ttu-id="93281-116">Typ av vänster mat ris element.</span><span class="sxs-lookup"><span data-stu-id="93281-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="93281-117">' U</span><span class="sxs-lookup"><span data-stu-id="93281-117">'U</span></span>

<span data-ttu-id="93281-118">Typ av höger mat ris element.</span><span class="sxs-lookup"><span data-stu-id="93281-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="93281-119">Se även</span><span class="sxs-lookup"><span data-stu-id="93281-119">See Also</span></span>

- [<span data-ttu-id="93281-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="93281-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="93281-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="93281-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="93281-122">Microsoft. Quantum. arrayer. unzippad</span><span class="sxs-lookup"><span data-stu-id="93281-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)