---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Funktionen NotEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849050"
---
# <a name="notequald-function"></a><span data-ttu-id="e2dc5-102">Funktionen NotEqualD</span><span class="sxs-lookup"><span data-stu-id="e2dc5-102">NotEqualD function</span></span>

<span data-ttu-id="e2dc5-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e2dc5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e2dc5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2dc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2dc5-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="e2dc5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e2dc5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e2dc5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e2dc5-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e2dc5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e2dc5-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e2dc5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e2dc5-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e2dc5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e2dc5-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e2dc5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e2dc5-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e2dc5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e2dc5-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="e2dc5-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2dc5-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e2dc5-113">Remarks</span></span>

<span data-ttu-id="e2dc5-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="e2dc5-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```