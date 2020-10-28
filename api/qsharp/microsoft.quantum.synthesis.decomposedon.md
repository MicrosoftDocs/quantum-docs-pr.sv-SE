---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Funktionen DecomposedOn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733915"
---
# <a name="decomposedon-function"></a><span data-ttu-id="10ab7-102">Funktionen DecomposedOn</span><span class="sxs-lookup"><span data-stu-id="10ab7-102">DecomposedOn function</span></span>

<span data-ttu-id="10ab7-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="10ab7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="10ab7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10ab7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10ab7-105">Deskapar en permutation för en variabel</span><span class="sxs-lookup"><span data-stu-id="10ab7-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="10ab7-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="10ab7-106">Description</span></span>

<span data-ttu-id="10ab7-107">Gett en permutation $ \pi $ ( `perm` ) och ett index $i $ ( `index` ), den här metoden returnerar tre permutationer $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.</span><span class="sxs-lookup"><span data-stu-id="10ab7-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="10ab7-108">Indata</span><span class="sxs-lookup"><span data-stu-id="10ab7-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="10ab7-109">behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="10ab7-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="10ab7-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10ab7-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="10ab7-111">Utdata: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="10ab7-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

