---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815980"
---
# <a name="equalr-function"></a><span data-ttu-id="b0b47-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="b0b47-102">EqualR function</span></span>

<span data-ttu-id="b0b47-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b0b47-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b0b47-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0b47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0b47-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="b0b47-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="b0b47-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b0b47-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="b0b47-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="b0b47-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="b0b47-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b0b47-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="b0b47-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="b0b47-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="b0b47-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b0b47-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b0b47-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b0b47-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b0b47-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="b0b47-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0b47-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b0b47-113">Remarks</span></span>

<span data-ttu-id="b0b47-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b0b47-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```