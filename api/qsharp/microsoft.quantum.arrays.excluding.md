---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exkluderande funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848655"
---
# <a name="excluding-function"></a><span data-ttu-id="08712-102">Exkluderande funktion</span><span class="sxs-lookup"><span data-stu-id="08712-102">Excluding function</span></span>

<span data-ttu-id="08712-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="08712-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="08712-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08712-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08712-105">Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.</span><span class="sxs-lookup"><span data-stu-id="08712-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="08712-106">Indata</span><span class="sxs-lookup"><span data-stu-id="08712-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="08712-107">ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="08712-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="08712-108">En matris med index som anger vilka element som ska uteslutas från utdata.</span><span class="sxs-lookup"><span data-stu-id="08712-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="08712-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="08712-109">array : 'T[]</span></span>

<span data-ttu-id="08712-110">Matris där värdena i utdatabufferten tas.</span><span class="sxs-lookup"><span data-stu-id="08712-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="08712-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="08712-111">Output : 'T[]</span></span>

<span data-ttu-id="08712-112">En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="08712-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="08712-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="08712-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08712-114">Inte</span><span class="sxs-lookup"><span data-stu-id="08712-114">'T</span></span>

<span data-ttu-id="08712-115">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="08712-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="08712-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="08712-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```