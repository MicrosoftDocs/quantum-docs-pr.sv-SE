---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Funktionen LessThanOrEqualL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849120"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="9734e-102">Funktionen LessThanOrEqualL</span><span class="sxs-lookup"><span data-stu-id="9734e-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="9734e-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9734e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9734e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9734e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9734e-105">Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="9734e-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="9734e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9734e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9734e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9734e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9734e-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="9734e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9734e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9734e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9734e-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="9734e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9734e-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9734e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9734e-112">`true` om och endast om `a` är mindre än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="9734e-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9734e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9734e-113">Remarks</span></span>

<span data-ttu-id="9734e-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="9734e-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```