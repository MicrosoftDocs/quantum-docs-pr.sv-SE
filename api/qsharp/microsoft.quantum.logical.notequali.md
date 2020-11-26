---
uid: Microsoft.Quantum.Logical.NotEqualI
title: Funktionen NotEqualI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197219"
---
# <a name="notequali-function"></a><span data-ttu-id="6a8db-102">Funktionen NotEqualI</span><span class="sxs-lookup"><span data-stu-id="6a8db-102">NotEqualI function</span></span>

<span data-ttu-id="6a8db-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6a8db-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6a8db-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a8db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a8db-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="6a8db-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6a8db-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6a8db-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6a8db-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a8db-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a8db-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6a8db-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6a8db-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a8db-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a8db-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6a8db-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6a8db-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6a8db-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6a8db-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="6a8db-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a8db-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6a8db-113">Remarks</span></span>

<span data-ttu-id="6a8db-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="6a8db-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```