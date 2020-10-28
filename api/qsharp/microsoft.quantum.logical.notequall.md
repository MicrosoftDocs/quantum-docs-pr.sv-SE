---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Funktionen NotEqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725974"
---
# <a name="notequall-function"></a><span data-ttu-id="575a0-102">Funktionen NotEqualL</span><span class="sxs-lookup"><span data-stu-id="575a0-102">NotEqualL function</span></span>

<span data-ttu-id="575a0-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="575a0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="575a0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="575a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="575a0-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="575a0-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="575a0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="575a0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="575a0-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="575a0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="575a0-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="575a0-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="575a0-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="575a0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="575a0-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="575a0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="575a0-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="575a0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="575a0-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="575a0-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="575a0-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="575a0-113">Remarks</span></span>

<span data-ttu-id="575a0-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="575a0-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```