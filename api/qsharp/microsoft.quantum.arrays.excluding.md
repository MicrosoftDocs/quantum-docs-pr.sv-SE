---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exkluderande funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 6585e619834a96953c9eae2d36a8ebe0a11dbda0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221325"
---
# <a name="excluding-function"></a><span data-ttu-id="0f0e7-102">Exkluderande funktion</span><span class="sxs-lookup"><span data-stu-id="0f0e7-102">Excluding function</span></span>

<span data-ttu-id="0f0e7-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0f0e7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0f0e7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f0e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f0e7-105">Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0f0e7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0f0e7-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="0f0e7-107">ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0f0e7-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0f0e7-108">En matris med index som anger vilka element som ska uteslutas från utdata.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="0f0e7-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="0f0e7-109">array : 'T[]</span></span>

<span data-ttu-id="0f0e7-110">Matris där värdena i utdatabufferten tas.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="0f0e7-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="0f0e7-111">Output : 'T[]</span></span>

<span data-ttu-id="0f0e7-112">En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f0e7-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0f0e7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f0e7-114">Inte</span><span class="sxs-lookup"><span data-stu-id="0f0e7-114">'T</span></span>

<span data-ttu-id="0f0e7-115">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-115">The type of the array elements.</span></span>