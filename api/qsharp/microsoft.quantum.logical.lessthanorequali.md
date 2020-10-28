---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Funktionen LessThanOrEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726028"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="4bc0d-102">Funktionen LessThanOrEqualI</span><span class="sxs-lookup"><span data-stu-id="4bc0d-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="4bc0d-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4bc0d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bc0d-105">Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="4bc0d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4bc0d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="4bc0d-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bc0d-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="4bc0d-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bc0d-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4bc0d-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4bc0d-112">`true` om och endast om `a` är mindre än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="4bc0d-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bc0d-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4bc0d-113">Remarks</span></span>

<span data-ttu-id="4bc0d-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="4bc0d-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```