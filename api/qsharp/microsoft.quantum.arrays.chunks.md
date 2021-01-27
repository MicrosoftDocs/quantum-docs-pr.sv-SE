---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842880"
---
# <a name="chunks-function"></a><span data-ttu-id="12ae4-102">Segment funktion</span><span class="sxs-lookup"><span data-stu-id="12ae4-102">Chunks function</span></span>

<span data-ttu-id="12ae4-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="12ae4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="12ae4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12ae4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12ae4-105">Delar upp en matris i flera delar med samma längd.</span><span class="sxs-lookup"><span data-stu-id="12ae4-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="12ae4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="12ae4-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="12ae4-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12ae4-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12ae4-108">Längden på varje segment.</span><span class="sxs-lookup"><span data-stu-id="12ae4-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="12ae4-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="12ae4-109">arr : 'T[]</span></span>

<span data-ttu-id="12ae4-110">Matrisen som ska delas.</span><span class="sxs-lookup"><span data-stu-id="12ae4-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="12ae4-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="12ae4-111">Output : 'T[][]</span></span>

<span data-ttu-id="12ae4-112">En matris som innehåller varje segment i den ursprungliga matrisen.</span><span class="sxs-lookup"><span data-stu-id="12ae4-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="12ae4-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="12ae4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12ae4-114">Inte</span><span class="sxs-lookup"><span data-stu-id="12ae4-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="12ae4-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="12ae4-115">Remarks</span></span>

<span data-ttu-id="12ae4-116">Observera att det sista elementet i utdata kan vara kortare än `nElements` om `Length(arr)` inte är delbar med `nElements` .</span><span class="sxs-lookup"><span data-stu-id="12ae4-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>