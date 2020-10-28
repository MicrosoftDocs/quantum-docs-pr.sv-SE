---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Partitionerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730086"
---
# <a name="partitioned-function"></a><span data-ttu-id="2a696-102">Partitionerad funktion</span><span class="sxs-lookup"><span data-stu-id="2a696-102">Partitioned function</span></span>

<span data-ttu-id="2a696-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2a696-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2a696-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a696-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a696-105">Delar upp en matris i flera delar.</span><span class="sxs-lookup"><span data-stu-id="2a696-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="2a696-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2a696-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="2a696-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a696-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a696-108">Antal element i varje del av matrisen</span><span class="sxs-lookup"><span data-stu-id="2a696-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="2a696-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="2a696-109">arr : 'T[]</span></span>

<span data-ttu-id="2a696-110">Inmatad matris som ska delas.</span><span class="sxs-lookup"><span data-stu-id="2a696-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="2a696-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="2a696-111">Output : 'T[][]</span></span>

<span data-ttu-id="2a696-112">Flera matriser där den första matrisen är den första `nElements[0]` av `arr` och den andra matrisen är nästa `nElements[1]` i `arr` osv. Den sista matrisen kommer att innehålla alla återstående element.</span><span class="sxs-lookup"><span data-stu-id="2a696-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a696-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2a696-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a696-114">Inte</span><span class="sxs-lookup"><span data-stu-id="2a696-114">'T</span></span>

