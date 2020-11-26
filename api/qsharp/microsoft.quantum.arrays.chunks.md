---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221614"
---
# <a name="chunks-function"></a><span data-ttu-id="e437f-102">Segment funktion</span><span class="sxs-lookup"><span data-stu-id="e437f-102">Chunks function</span></span>

<span data-ttu-id="e437f-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e437f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e437f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e437f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e437f-105">Delar upp en matris i flera delar med samma längd.</span><span class="sxs-lookup"><span data-stu-id="e437f-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e437f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e437f-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="e437f-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e437f-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e437f-108">Längden på varje segment.</span><span class="sxs-lookup"><span data-stu-id="e437f-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e437f-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="e437f-109">arr : 'T[]</span></span>

<span data-ttu-id="e437f-110">Matrisen som ska delas.</span><span class="sxs-lookup"><span data-stu-id="e437f-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="e437f-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="e437f-111">Output : 'T[][]</span></span>

<span data-ttu-id="e437f-112">En matris som innehåller varje segment i den ursprungliga matrisen.</span><span class="sxs-lookup"><span data-stu-id="e437f-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e437f-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e437f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e437f-114">Inte</span><span class="sxs-lookup"><span data-stu-id="e437f-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e437f-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e437f-115">Remarks</span></span>

<span data-ttu-id="e437f-116">Observera att det sista elementet i utdata kan vara kortare än `nElements` om `Length(arr)` inte är delbar med `nElements` .</span><span class="sxs-lookup"><span data-stu-id="e437f-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>