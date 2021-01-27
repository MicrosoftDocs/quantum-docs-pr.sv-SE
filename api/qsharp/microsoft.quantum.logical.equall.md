---
uid: Microsoft.Quantum.Logical.EqualL
title: Funktionen EqualL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815975"
---
# <a name="equall-function"></a><span data-ttu-id="a36a8-102">Funktionen EqualL</span><span class="sxs-lookup"><span data-stu-id="a36a8-102">EqualL function</span></span>

<span data-ttu-id="a36a8-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a36a8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a36a8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a36a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a36a8-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="a36a8-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a36a8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a36a8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a36a8-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a36a8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a36a8-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a36a8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a36a8-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a36a8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a36a8-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a36a8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a36a8-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a36a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a36a8-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="a36a8-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a36a8-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a36a8-113">Remarks</span></span>

<span data-ttu-id="a36a8-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a36a8-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```