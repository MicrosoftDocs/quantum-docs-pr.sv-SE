---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Funktionen LessThanOrEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849126"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="3c28c-102">Funktionen LessThanOrEqualD</span><span class="sxs-lookup"><span data-stu-id="3c28c-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="3c28c-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3c28c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3c28c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c28c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c28c-105">Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="3c28c-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3c28c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3c28c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3c28c-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3c28c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3c28c-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3c28c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3c28c-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3c28c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3c28c-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3c28c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3c28c-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3c28c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3c28c-112">`true` om och endast om `a` är mindre än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="3c28c-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c28c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3c28c-113">Remarks</span></span>

<span data-ttu-id="3c28c-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="3c28c-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```