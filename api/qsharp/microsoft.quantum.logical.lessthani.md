---
uid: Microsoft.Quantum.Logical.LessThanI
title: Funktionen LessThanI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732923"
---
# <a name="lessthani-function"></a><span data-ttu-id="a16b3-102">Funktionen LessThanI</span><span class="sxs-lookup"><span data-stu-id="a16b3-102">LessThanI function</span></span>

<span data-ttu-id="a16b3-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a16b3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a16b3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a16b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a16b3-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="a16b3-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a16b3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a16b3-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a16b3-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a16b3-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a16b3-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a16b3-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a16b3-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a16b3-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a16b3-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a16b3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a16b3-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a16b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a16b3-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="a16b3-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a16b3-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a16b3-113">Remarks</span></span>

<span data-ttu-id="a16b3-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a16b3-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```