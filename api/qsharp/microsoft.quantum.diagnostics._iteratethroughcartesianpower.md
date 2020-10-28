---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727402"
---
# <a name="_iteratethroughcartesianpower-operation"></a><span data-ttu-id="d6980-102">_iterateThroughCartesianPower åtgärd</span><span class="sxs-lookup"><span data-stu-id="d6980-102">_iterateThroughCartesianPower operation</span></span>

<span data-ttu-id="d6980-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d6980-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d6980-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6980-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6980-105">Itererar en variabel genom en kartesiska-produkt [0, gränser [0]-1] × [0, gränser [1]-1] × [0, gränser [längd (gränser)-1]-1] och anrop OP (arr) för varje element i kartesiska-produkten</span><span class="sxs-lookup"><span data-stu-id="d6980-105">Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product</span></span>

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="d6980-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d6980-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="d6980-107">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6980-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="value--int"></a><span data-ttu-id="d6980-108">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6980-108">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--int--unit"></a><span data-ttu-id="d6980-109">OP: [int](xref:microsoft.quantum.lang-ref.int)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6980-109">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="d6980-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6980-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

