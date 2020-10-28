---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exkludera funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730291"
---
# <a name="exclude-function"></a><span data-ttu-id="af311-102">Exkludera funktion</span><span class="sxs-lookup"><span data-stu-id="af311-102">Exclude function</span></span>

<span data-ttu-id="af311-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="af311-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="af311-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af311-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af311-105">Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.</span><span class="sxs-lookup"><span data-stu-id="af311-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="af311-106">Indata</span><span class="sxs-lookup"><span data-stu-id="af311-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="af311-107">ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="af311-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="af311-108">En matris med index som anger vilka element som ska uteslutas från utdata.</span><span class="sxs-lookup"><span data-stu-id="af311-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="af311-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="af311-109">array : 'T[]</span></span>

<span data-ttu-id="af311-110">Matris där värdena i utdatabufferten tas.</span><span class="sxs-lookup"><span data-stu-id="af311-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="af311-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="af311-111">Output : 'T[]</span></span>

<span data-ttu-id="af311-112">En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="af311-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="af311-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="af311-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af311-114">Inte</span><span class="sxs-lookup"><span data-stu-id="af311-114">'T</span></span>

<span data-ttu-id="af311-115">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="af311-115">The type of the array elements.</span></span>