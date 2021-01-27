---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exkludera funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848666"
---
# <a name="exclude-function"></a><span data-ttu-id="b16fc-102">Exkludera funktion</span><span class="sxs-lookup"><span data-stu-id="b16fc-102">Exclude function</span></span>

<span data-ttu-id="b16fc-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b16fc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b16fc-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b16fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b16fc-105">Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.</span><span class="sxs-lookup"><span data-stu-id="b16fc-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b16fc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b16fc-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="b16fc-107">ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b16fc-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b16fc-108">En matris med index som anger vilka element som ska uteslutas från utdata.</span><span class="sxs-lookup"><span data-stu-id="b16fc-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="b16fc-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="b16fc-109">array : 'T[]</span></span>

<span data-ttu-id="b16fc-110">Matris där värdena i utdatabufferten tas.</span><span class="sxs-lookup"><span data-stu-id="b16fc-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="b16fc-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="b16fc-111">Output : 'T[]</span></span>

<span data-ttu-id="b16fc-112">En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b16fc-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b16fc-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b16fc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b16fc-114">Inte</span><span class="sxs-lookup"><span data-stu-id="b16fc-114">'T</span></span>

<span data-ttu-id="b16fc-115">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b16fc-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="b16fc-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="b16fc-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```