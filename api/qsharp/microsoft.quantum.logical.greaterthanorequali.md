---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: Funktionen GreaterThanOrEqualI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197797"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="949b2-102">Funktionen GreaterThanOrEqualI</span><span class="sxs-lookup"><span data-stu-id="949b2-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="949b2-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="949b2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="949b2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="949b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="949b2-105">Returnerar true om och endast om ett tal är större än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="949b2-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="949b2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="949b2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="949b2-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="949b2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="949b2-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="949b2-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="949b2-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="949b2-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="949b2-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="949b2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="949b2-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="949b2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="949b2-112">`true` om och bara om `a` är större än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="949b2-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="949b2-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="949b2-113">Remarks</span></span>

<span data-ttu-id="949b2-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="949b2-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```