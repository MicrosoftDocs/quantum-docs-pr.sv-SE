---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206484"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="0e67e-102">IterateThroughCartesianPower-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0e67e-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="0e67e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e67e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e67e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e67e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e67e-105">Tillämpar en åtgärd för varje index i kartesiska-kraften i ett heltals intervall.</span><span class="sxs-lookup"><span data-stu-id="0e67e-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0e67e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e67e-106">Description</span></span>

<span data-ttu-id="0e67e-107">En åtgärd tillämpas iterativt för varje element i en kartesiska-potens av intervallet `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="0e67e-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="0e67e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="0e67e-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="0e67e-109">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e67e-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e67e-110">Kartesiska-kraften som intervallet `0..(bound - 1)` ska höjas till.</span><span class="sxs-lookup"><span data-stu-id="0e67e-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="0e67e-111">Bound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e67e-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e67e-112">En specifikation av intervallet som ska upprepas, anges som längden på intervallet.</span><span class="sxs-lookup"><span data-stu-id="0e67e-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0e67e-113">OP: [int](xref:microsoft.quantum.lang-ref.int)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e67e-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0e67e-114">En åtgärd som ska anropas för varje element med den aktuella kartesiska-kraften.</span><span class="sxs-lookup"><span data-stu-id="0e67e-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e67e-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e67e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0e67e-116">Se även</span><span class="sxs-lookup"><span data-stu-id="0e67e-116">See Also</span></span>

- [<span data-ttu-id="0e67e-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="0e67e-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)