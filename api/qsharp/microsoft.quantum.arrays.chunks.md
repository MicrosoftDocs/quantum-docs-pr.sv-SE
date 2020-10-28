---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730414"
---
# <a name="chunks-function"></a><span data-ttu-id="5b5d6-102">Segment funktion</span><span class="sxs-lookup"><span data-stu-id="5b5d6-102">Chunks function</span></span>

<span data-ttu-id="5b5d6-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5b5d6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5b5d6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b5d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b5d6-105">Delar upp en matris i flera delar med samma längd.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="5b5d6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5b5d6-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="5b5d6-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b5d6-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b5d6-108">Längden på varje segment.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="5b5d6-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="5b5d6-109">arr : 'T[]</span></span>

<span data-ttu-id="5b5d6-110">Matrisen som ska delas.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="5b5d6-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="5b5d6-111">Output : 'T[][]</span></span>

<span data-ttu-id="5b5d6-112">En matris som innehåller varje segment i den ursprungliga matrisen.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5b5d6-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5b5d6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b5d6-114">Inte</span><span class="sxs-lookup"><span data-stu-id="5b5d6-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5b5d6-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5b5d6-115">Remarks</span></span>

<span data-ttu-id="5b5d6-116">Observera att det sista elementet i utdata kan vara kortare än `nElements` om `Length(arr)` inte är delbar med `nElements` .</span><span class="sxs-lookup"><span data-stu-id="5b5d6-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>