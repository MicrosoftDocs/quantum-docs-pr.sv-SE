---
uid: Microsoft.Quantum.Logical.LessThanD
title: Funktionen LessThanD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849160"
---
# <a name="lessthand-function"></a><span data-ttu-id="a79c3-102">Funktionen LessThanD</span><span class="sxs-lookup"><span data-stu-id="a79c3-102">LessThanD function</span></span>

<span data-ttu-id="a79c3-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a79c3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a79c3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a79c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a79c3-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="a79c3-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="a79c3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a79c3-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="a79c3-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a79c3-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a79c3-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a79c3-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="a79c3-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a79c3-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a79c3-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a79c3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a79c3-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a79c3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a79c3-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="a79c3-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a79c3-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a79c3-113">Remarks</span></span>

<span data-ttu-id="a79c3-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a79c3-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```