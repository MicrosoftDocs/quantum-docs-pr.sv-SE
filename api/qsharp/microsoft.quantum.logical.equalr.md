---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726070"
---
# <a name="equalr-function"></a><span data-ttu-id="88dfb-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="88dfb-102">EqualR function</span></span>

<span data-ttu-id="88dfb-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="88dfb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="88dfb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88dfb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88dfb-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="88dfb-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="88dfb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="88dfb-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="88dfb-107">a: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="88dfb-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="88dfb-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="88dfb-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="88dfb-109">b: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="88dfb-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="88dfb-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="88dfb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="88dfb-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="88dfb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="88dfb-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="88dfb-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="88dfb-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="88dfb-113">Remarks</span></span>

<span data-ttu-id="88dfb-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="88dfb-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```