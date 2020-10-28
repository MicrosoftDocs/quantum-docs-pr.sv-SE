---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: Funktionen GreaterThanI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726049"
---
# <a name="greaterthani-function"></a><span data-ttu-id="00816-102">Funktionen GreaterThanI</span><span class="sxs-lookup"><span data-stu-id="00816-102">GreaterThanI function</span></span>

<span data-ttu-id="00816-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="00816-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="00816-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00816-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00816-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="00816-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="00816-106">Indata</span><span class="sxs-lookup"><span data-stu-id="00816-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="00816-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00816-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00816-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="00816-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="00816-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00816-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00816-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="00816-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="00816-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00816-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00816-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="00816-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="00816-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="00816-113">Remarks</span></span>

<span data-ttu-id="00816-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="00816-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```