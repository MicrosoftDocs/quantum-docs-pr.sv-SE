---
uid: Microsoft.Quantum.Logical.EqualL
title: Funktionen EqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726073"
---
# <a name="equall-function"></a><span data-ttu-id="c2a49-102">Funktionen EqualL</span><span class="sxs-lookup"><span data-stu-id="c2a49-102">EqualL function</span></span>

<span data-ttu-id="c2a49-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c2a49-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c2a49-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2a49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2a49-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="c2a49-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c2a49-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c2a49-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c2a49-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2a49-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2a49-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="c2a49-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c2a49-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2a49-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2a49-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="c2a49-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c2a49-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2a49-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2a49-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="c2a49-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2a49-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c2a49-113">Remarks</span></span>

<span data-ttu-id="c2a49-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="c2a49-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```