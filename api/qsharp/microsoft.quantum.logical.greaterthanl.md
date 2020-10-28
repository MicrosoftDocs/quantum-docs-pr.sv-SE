---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: Funktionen GreaterThanL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726649"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="4640b-102">Funktionen GreaterThanL</span><span class="sxs-lookup"><span data-stu-id="4640b-102">GreaterThanL function</span></span>

<span data-ttu-id="4640b-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4640b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4640b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4640b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4640b-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="4640b-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4640b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4640b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4640b-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4640b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4640b-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4640b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4640b-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4640b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4640b-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4640b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4640b-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4640b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4640b-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="4640b-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4640b-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4640b-113">Remarks</span></span>

<span data-ttu-id="4640b-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="4640b-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```