---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: Funktionen GreaterThanI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815945"
---
# <a name="greaterthani-function"></a><span data-ttu-id="ad674-102">Funktionen GreaterThanI</span><span class="sxs-lookup"><span data-stu-id="ad674-102">GreaterThanI function</span></span>

<span data-ttu-id="ad674-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ad674-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ad674-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad674-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad674-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="ad674-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ad674-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ad674-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ad674-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad674-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad674-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="ad674-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ad674-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad674-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad674-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="ad674-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ad674-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad674-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad674-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="ad674-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad674-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ad674-113">Remarks</span></span>

<span data-ttu-id="ad674-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="ad674-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```