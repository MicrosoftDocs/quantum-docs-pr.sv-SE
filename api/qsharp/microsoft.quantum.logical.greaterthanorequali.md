---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: Funktionen GreaterThanOrEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732931"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="1364a-102">Funktionen GreaterThanOrEqualI</span><span class="sxs-lookup"><span data-stu-id="1364a-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="1364a-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1364a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1364a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1364a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1364a-105">Returnerar true om och endast om ett tal är större än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="1364a-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="1364a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1364a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="1364a-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1364a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1364a-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="1364a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="1364a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1364a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1364a-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="1364a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1364a-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1364a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1364a-112">`true` om och bara om `a` är större än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="1364a-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1364a-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1364a-113">Remarks</span></span>

<span data-ttu-id="1364a-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="1364a-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```