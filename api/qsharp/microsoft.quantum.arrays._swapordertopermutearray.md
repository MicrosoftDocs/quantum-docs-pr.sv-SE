---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221716"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="0d9d3-102">_SwapOrderToPermuteArray funktion</span><span class="sxs-lookup"><span data-stu-id="0d9d3-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="0d9d3-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0d9d3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0d9d3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d9d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d9d3-105">Returnerar ordnings elementen i en matris som måste växlas för att skapa en ordnad matris.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="0d9d3-106">Förutsätter att växlingar sker på plats.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="0d9d3-107">Indata</span><span class="sxs-lookup"><span data-stu-id="0d9d3-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="0d9d3-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0d9d3-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0d9d3-109">Matris med permutationen av index för den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="0d9d3-110">Det bör finnas $n $ Elements, var och en är ett unikt heltal från $0 $ till $n-$1.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="0d9d3-111">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="0d9d3-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="0d9d3-112">Tuppeln representerar de två index som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="0d9d3-113">Växlingarna börjar vid det lägsta indexet.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d9d3-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0d9d3-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="0d9d3-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="0d9d3-115">Psuedocode</span></span>

<span data-ttu-id="0d9d3-116">för (index i 0.. längd (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] med newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="0d9d3-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>