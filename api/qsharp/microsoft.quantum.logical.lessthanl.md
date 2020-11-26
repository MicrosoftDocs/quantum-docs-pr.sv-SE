---
uid: Microsoft.Quantum.Logical.LessThanL
title: Funktionen LessThanL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197729"
---
# <a name="lessthanl-function"></a><span data-ttu-id="90428-102">Funktionen LessThanL</span><span class="sxs-lookup"><span data-stu-id="90428-102">LessThanL function</span></span>

<span data-ttu-id="90428-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="90428-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="90428-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90428-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="90428-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="90428-106">Indata</span><span class="sxs-lookup"><span data-stu-id="90428-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="90428-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90428-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90428-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="90428-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="90428-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90428-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90428-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="90428-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="90428-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90428-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90428-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="90428-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="90428-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="90428-113">Remarks</span></span>

<span data-ttu-id="90428-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="90428-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```