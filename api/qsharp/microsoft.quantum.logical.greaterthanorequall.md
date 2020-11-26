---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: Funktionen GreaterThanOrEqualL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197763"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="72f9e-102">Funktionen GreaterThanOrEqualL</span><span class="sxs-lookup"><span data-stu-id="72f9e-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="72f9e-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="72f9e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="72f9e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72f9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72f9e-105">Returnerar true om och endast om ett tal är större än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="72f9e-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="72f9e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="72f9e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="72f9e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="72f9e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="72f9e-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="72f9e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="72f9e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="72f9e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="72f9e-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="72f9e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="72f9e-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="72f9e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="72f9e-112">`true` om och bara om `a` är större än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="72f9e-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="72f9e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="72f9e-113">Remarks</span></span>

<span data-ttu-id="72f9e-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="72f9e-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```