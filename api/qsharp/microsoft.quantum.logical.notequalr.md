---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Funktionen NotEqualR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197202"
---
# <a name="notequalr-function"></a><span data-ttu-id="dd333-102">Funktionen NotEqualR</span><span class="sxs-lookup"><span data-stu-id="dd333-102">NotEqualR function</span></span>

<span data-ttu-id="dd333-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dd333-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dd333-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd333-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd333-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="dd333-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="dd333-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dd333-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="dd333-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd333-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="dd333-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="dd333-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="dd333-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd333-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="dd333-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="dd333-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dd333-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd333-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd333-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="dd333-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd333-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dd333-113">Remarks</span></span>

<span data-ttu-id="dd333-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="dd333-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```