---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198014"
---
# <a name="equalr-function"></a><span data-ttu-id="67b4c-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="67b4c-102">EqualR function</span></span>

<span data-ttu-id="67b4c-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="67b4c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="67b4c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67b4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67b4c-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="67b4c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="67b4c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="67b4c-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="67b4c-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="67b4c-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="67b4c-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="67b4c-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="67b4c-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="67b4c-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="67b4c-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="67b4c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="67b4c-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67b4c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="67b4c-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="67b4c-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="67b4c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="67b4c-113">Remarks</span></span>

<span data-ttu-id="67b4c-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="67b4c-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```