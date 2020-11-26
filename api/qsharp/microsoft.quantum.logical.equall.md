---
uid: Microsoft.Quantum.Logical.EqualL
title: Funktionen EqualL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198120"
---
# <a name="equall-function"></a><span data-ttu-id="dae63-102">Funktionen EqualL</span><span class="sxs-lookup"><span data-stu-id="dae63-102">EqualL function</span></span>

<span data-ttu-id="dae63-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dae63-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dae63-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dae63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dae63-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="dae63-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="dae63-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dae63-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="dae63-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dae63-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dae63-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="dae63-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="dae63-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dae63-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dae63-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="dae63-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dae63-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dae63-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dae63-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="dae63-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dae63-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dae63-113">Remarks</span></span>

<span data-ttu-id="dae63-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="dae63-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```