---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846298"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="c8c84-102">_SwapOrderToPermuteArray funktion</span><span class="sxs-lookup"><span data-stu-id="c8c84-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="c8c84-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c8c84-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c8c84-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8c84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8c84-105">Returnerar ordnings elementen i en matris som måste växlas för att skapa en ordnad matris.</span><span class="sxs-lookup"><span data-stu-id="c8c84-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="c8c84-106">Förutsätter att växlingar sker på plats.</span><span class="sxs-lookup"><span data-stu-id="c8c84-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c8c84-107">Indata</span><span class="sxs-lookup"><span data-stu-id="c8c84-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="c8c84-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c8c84-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c8c84-109">Matris med permutationen av index för den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="c8c84-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="c8c84-110">Det bör finnas $n $ Elements, var och en är ett unikt heltal från $0 $ till $n-$1.</span><span class="sxs-lookup"><span data-stu-id="c8c84-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="c8c84-111">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c8c84-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c8c84-112">Tuppeln representerar de två index som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="c8c84-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="c8c84-113">Växlingarna börjar vid det lägsta indexet.</span><span class="sxs-lookup"><span data-stu-id="c8c84-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="c8c84-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="c8c84-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="c8c84-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c8c84-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="c8c84-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="c8c84-116">Psuedocode</span></span>

<span data-ttu-id="c8c84-117">för (index i 0.. längd (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] med newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="c8c84-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>