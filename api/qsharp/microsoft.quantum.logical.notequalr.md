---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Funktionen NotEqualR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725968"
---
# <a name="notequalr-function"></a><span data-ttu-id="afe63-102">Funktionen NotEqualR</span><span class="sxs-lookup"><span data-stu-id="afe63-102">NotEqualR function</span></span>

<span data-ttu-id="afe63-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="afe63-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="afe63-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afe63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afe63-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="afe63-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="afe63-106">Indata</span><span class="sxs-lookup"><span data-stu-id="afe63-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="afe63-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="afe63-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="afe63-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="afe63-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="afe63-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="afe63-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="afe63-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="afe63-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="afe63-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="afe63-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="afe63-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="afe63-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="afe63-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="afe63-113">Remarks</span></span>

<span data-ttu-id="afe63-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="afe63-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```