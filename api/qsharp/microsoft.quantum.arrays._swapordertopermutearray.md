---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730430"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="33f9b-102">_SwapOrderToPermuteArray funktion</span><span class="sxs-lookup"><span data-stu-id="33f9b-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="33f9b-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="33f9b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="33f9b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33f9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33f9b-105">Returnerar ordnings elementen i en matris som måste växlas för att skapa en ordnad matris.</span><span class="sxs-lookup"><span data-stu-id="33f9b-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="33f9b-106">Förutsätter att växlingar sker på plats.</span><span class="sxs-lookup"><span data-stu-id="33f9b-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="33f9b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="33f9b-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="33f9b-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="33f9b-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="33f9b-109">Matris med permutationen av index för den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="33f9b-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="33f9b-110">Det bör finnas $n $ Elements, var och en är ett unikt heltal från $0 $ till $n-$1.</span><span class="sxs-lookup"><span data-stu-id="33f9b-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="33f9b-111">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="33f9b-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="33f9b-112">Tuppeln representerar de två index som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="33f9b-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="33f9b-113">Växlingarna börjar vid det lägsta indexet.</span><span class="sxs-lookup"><span data-stu-id="33f9b-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="33f9b-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="33f9b-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="33f9b-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="33f9b-115">Psuedocode</span></span>

<span data-ttu-id="33f9b-116">för (index i 0.. längd (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] med newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="33f9b-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>