---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733910"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="8e634-102">DecompositionState-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="8e634-102">DecompositionState user defined type</span></span>

<span data-ttu-id="8e634-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8e634-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8e634-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e634-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e634-105">Tillstånd under dekompositionen baserat på variabel index</span><span class="sxs-lookup"><span data-stu-id="8e634-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="8e634-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="8e634-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="8e634-107">Behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8e634-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="8e634-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8e634-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="8e634-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8e634-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="8e634-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8e634-110">Description</span></span>

<span data-ttu-id="8e634-111">Statusen innehåller aktuell permutation och de funktioner som för närvarande har genererats för kontrollerade grindar till vänster och kontrollerade grindar till höger.</span><span class="sxs-lookup"><span data-stu-id="8e634-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>