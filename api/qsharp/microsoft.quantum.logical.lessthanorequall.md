---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Funktionen LessThanOrEqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726022"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="03526-102">Funktionen LessThanOrEqualL</span><span class="sxs-lookup"><span data-stu-id="03526-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="03526-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="03526-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="03526-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03526-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03526-105">Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="03526-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="03526-106">Indata</span><span class="sxs-lookup"><span data-stu-id="03526-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="03526-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="03526-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="03526-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="03526-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="03526-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="03526-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="03526-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="03526-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="03526-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03526-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03526-112">`true` om och endast om `a` är mindre än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="03526-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="03526-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="03526-113">Remarks</span></span>

<span data-ttu-id="03526-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="03526-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```