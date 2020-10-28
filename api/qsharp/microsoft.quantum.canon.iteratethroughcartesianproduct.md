---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728644"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="d0862-102">IterateThroughCartesianProduct-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d0862-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="d0862-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0862-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0862-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0862-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0862-105">Tillämpar en åtgärd för varje index i kartesiska-produkten av flera intervall.</span><span class="sxs-lookup"><span data-stu-id="d0862-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="d0862-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0862-106">Description</span></span>

<span data-ttu-id="d0862-107">En åtgärd tillämpas iterativt för varje element i kartesiska-produkten av `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="d0862-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="d0862-108">Indata</span><span class="sxs-lookup"><span data-stu-id="d0862-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="d0862-109">gränser: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d0862-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d0862-110">En matris som anger de intervall som ska upprepas, där varje intervall anges som en heltals längd.</span><span class="sxs-lookup"><span data-stu-id="d0862-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="d0862-111">OP: [int](xref:microsoft.quantum.lang-ref.int)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0862-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d0862-112">En åtgärd som ska anropas för varje element i den aktuella kartesiska-produkten.</span><span class="sxs-lookup"><span data-stu-id="d0862-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0862-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0862-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d0862-114">Se även</span><span class="sxs-lookup"><span data-stu-id="d0862-114">See Also</span></span>

- [<span data-ttu-id="d0862-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="d0862-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)