---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: Funktionen GreaterThanL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849202"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="38e26-102">Funktionen GreaterThanL</span><span class="sxs-lookup"><span data-stu-id="38e26-102">GreaterThanL function</span></span>

<span data-ttu-id="38e26-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="38e26-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="38e26-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38e26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38e26-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="38e26-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="38e26-106">Indata</span><span class="sxs-lookup"><span data-stu-id="38e26-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="38e26-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38e26-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38e26-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="38e26-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="38e26-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38e26-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38e26-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="38e26-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="38e26-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38e26-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38e26-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="38e26-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="38e26-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="38e26-113">Remarks</span></span>

<span data-ttu-id="38e26-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="38e26-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```