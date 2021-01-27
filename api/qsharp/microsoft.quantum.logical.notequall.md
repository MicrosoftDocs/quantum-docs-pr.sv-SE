---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Funktionen NotEqualL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849034"
---
# <a name="notequall-function"></a><span data-ttu-id="4f5e4-102">Funktionen NotEqualL</span><span class="sxs-lookup"><span data-stu-id="4f5e4-102">NotEqualL function</span></span>

<span data-ttu-id="4f5e4-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4f5e4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f5e4-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4f5e4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4f5e4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4f5e4-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f5e4-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4f5e4-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f5e4-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4f5e4-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f5e4-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="4f5e4-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f5e4-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4f5e4-113">Remarks</span></span>

<span data-ttu-id="4f5e4-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```