---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Funktionen NotEqualR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848500"
---
# <a name="notequalr-function"></a><span data-ttu-id="558e2-102">Funktionen NotEqualR</span><span class="sxs-lookup"><span data-stu-id="558e2-102">NotEqualR function</span></span>

<span data-ttu-id="558e2-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="558e2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="558e2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="558e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="558e2-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="558e2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="558e2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="558e2-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="558e2-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="558e2-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="558e2-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="558e2-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="558e2-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="558e2-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="558e2-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="558e2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="558e2-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="558e2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="558e2-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="558e2-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="558e2-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="558e2-113">Remarks</span></span>

<span data-ttu-id="558e2-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="558e2-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```