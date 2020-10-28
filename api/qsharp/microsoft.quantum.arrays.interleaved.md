---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Överlagrad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730198"
---
# <a name="interleaved-function"></a><span data-ttu-id="f22fe-102">Överlagrad funktion</span><span class="sxs-lookup"><span data-stu-id="f22fe-102">Interleaved function</span></span>

<span data-ttu-id="f22fe-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f22fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f22fe-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f22fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f22fe-105">Överlåter två matriser av (nästan) samma storlek.</span><span class="sxs-lookup"><span data-stu-id="f22fe-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f22fe-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f22fe-106">Description</span></span>

<span data-ttu-id="f22fe-107">Den här funktionen returnerar Interfoliering av två matriser, som börjar med det första elementet från den första matrisen, sedan det första elementet från den andra matrisen och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f22fe-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="f22fe-108">Den första matrisen måste antingen vara av samma längd som den andra, eller ha ett annat element.</span><span class="sxs-lookup"><span data-stu-id="f22fe-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="f22fe-109">Indata</span><span class="sxs-lookup"><span data-stu-id="f22fe-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="f22fe-110">första: ' ' []</span><span class="sxs-lookup"><span data-stu-id="f22fe-110">first : 'T[]</span></span>

<span data-ttu-id="f22fe-111">Den första matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="f22fe-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="f22fe-112">sekund: ' t []</span><span class="sxs-lookup"><span data-stu-id="f22fe-112">second : 'T[]</span></span>

<span data-ttu-id="f22fe-113">Den andra matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="f22fe-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="f22fe-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="f22fe-114">Output : 'T[]</span></span>

<span data-ttu-id="f22fe-115">Överlagrad matris</span><span class="sxs-lookup"><span data-stu-id="f22fe-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f22fe-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f22fe-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f22fe-117">Inte</span><span class="sxs-lookup"><span data-stu-id="f22fe-117">'T</span></span>

<span data-ttu-id="f22fe-118">Typen för varje element i `first` och `second` .</span><span class="sxs-lookup"><span data-stu-id="f22fe-118">The type of each element of `first` and `second`.</span></span>