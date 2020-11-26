---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Funktionen NotEqualL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197236"
---
# <a name="notequall-function"></a><span data-ttu-id="7c4f6-102">Funktionen NotEqualL</span><span class="sxs-lookup"><span data-stu-id="7c4f6-102">NotEqualL function</span></span>

<span data-ttu-id="7c4f6-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7c4f6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c4f6-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="7c4f6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7c4f6-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7c4f6-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7c4f6-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="7c4f6-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7c4f6-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7c4f6-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c4f6-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="7c4f6-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c4f6-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7c4f6-113">Remarks</span></span>

<span data-ttu-id="7c4f6-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="7c4f6-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```