---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exkluderande funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730286"
---
# <a name="excluding-function"></a><span data-ttu-id="26bfa-102">Exkluderande funktion</span><span class="sxs-lookup"><span data-stu-id="26bfa-102">Excluding function</span></span>

<span data-ttu-id="26bfa-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="26bfa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="26bfa-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26bfa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26bfa-105">Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.</span><span class="sxs-lookup"><span data-stu-id="26bfa-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="26bfa-106">Indata</span><span class="sxs-lookup"><span data-stu-id="26bfa-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="26bfa-107">ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26bfa-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="26bfa-108">En matris med index som anger vilka element som ska uteslutas från utdata.</span><span class="sxs-lookup"><span data-stu-id="26bfa-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="26bfa-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="26bfa-109">array : 'T[]</span></span>

<span data-ttu-id="26bfa-110">Matris där värdena i utdatabufferten tas.</span><span class="sxs-lookup"><span data-stu-id="26bfa-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="26bfa-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="26bfa-111">Output : 'T[]</span></span>

<span data-ttu-id="26bfa-112">En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="26bfa-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="26bfa-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="26bfa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26bfa-114">Inte</span><span class="sxs-lookup"><span data-stu-id="26bfa-114">'T</span></span>

<span data-ttu-id="26bfa-115">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="26bfa-115">The type of the array elements.</span></span>