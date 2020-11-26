---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Överlagrad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220968"
---
# <a name="interleaved-function"></a><span data-ttu-id="c9a95-102">Överlagrad funktion</span><span class="sxs-lookup"><span data-stu-id="c9a95-102">Interleaved function</span></span>

<span data-ttu-id="c9a95-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c9a95-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c9a95-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9a95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9a95-105">Överlåter två matriser av (nästan) samma storlek.</span><span class="sxs-lookup"><span data-stu-id="c9a95-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c9a95-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c9a95-106">Description</span></span>

<span data-ttu-id="c9a95-107">Den här funktionen returnerar Interfoliering av två matriser, som börjar med det första elementet från den första matrisen, sedan det första elementet från den andra matrisen och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c9a95-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="c9a95-108">Den första matrisen måste antingen vara av samma längd som den andra, eller ha ett annat element.</span><span class="sxs-lookup"><span data-stu-id="c9a95-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="c9a95-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c9a95-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="c9a95-110">första: ' ' []</span><span class="sxs-lookup"><span data-stu-id="c9a95-110">first : 'T[]</span></span>

<span data-ttu-id="c9a95-111">Den första matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="c9a95-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="c9a95-112">sekund: ' t []</span><span class="sxs-lookup"><span data-stu-id="c9a95-112">second : 'T[]</span></span>

<span data-ttu-id="c9a95-113">Den andra matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="c9a95-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="c9a95-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="c9a95-114">Output : 'T[]</span></span>

<span data-ttu-id="c9a95-115">Överlagrad matris</span><span class="sxs-lookup"><span data-stu-id="c9a95-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9a95-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c9a95-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9a95-117">Inte</span><span class="sxs-lookup"><span data-stu-id="c9a95-117">'T</span></span>

<span data-ttu-id="c9a95-118">Typen för varje element i `first` och `second` .</span><span class="sxs-lookup"><span data-stu-id="c9a95-118">The type of each element of `first` and `second`.</span></span>