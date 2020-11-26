---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Partitionerad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220509"
---
# <a name="partitioned-function"></a><span data-ttu-id="f8978-102">Partitionerad funktion</span><span class="sxs-lookup"><span data-stu-id="f8978-102">Partitioned function</span></span>

<span data-ttu-id="f8978-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f8978-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f8978-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8978-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8978-105">Delar upp en matris i flera delar.</span><span class="sxs-lookup"><span data-stu-id="f8978-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="f8978-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f8978-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="f8978-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8978-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8978-108">Antal element i varje del av matrisen</span><span class="sxs-lookup"><span data-stu-id="f8978-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="f8978-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="f8978-109">arr : 'T[]</span></span>

<span data-ttu-id="f8978-110">Inmatad matris som ska delas.</span><span class="sxs-lookup"><span data-stu-id="f8978-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="f8978-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="f8978-111">Output : 'T[][]</span></span>

<span data-ttu-id="f8978-112">Flera matriser där den första matrisen är den första `nElements[0]` av `arr` och den andra matrisen är nästa `nElements[1]` i `arr` osv. Den sista matrisen kommer att innehålla alla återstående element.</span><span class="sxs-lookup"><span data-stu-id="f8978-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f8978-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f8978-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8978-114">Inte</span><span class="sxs-lookup"><span data-stu-id="f8978-114">'T</span></span>

