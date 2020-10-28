---
uid: Microsoft.Quantum.Logical.NotEqualI
title: Funktionen NotEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725983"
---
# <a name="notequali-function"></a><span data-ttu-id="aa38b-102">Funktionen NotEqualI</span><span class="sxs-lookup"><span data-stu-id="aa38b-102">NotEqualI function</span></span>

<span data-ttu-id="aa38b-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="aa38b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="aa38b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa38b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa38b-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="aa38b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="aa38b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="aa38b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="aa38b-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa38b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa38b-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="aa38b-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="aa38b-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa38b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa38b-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="aa38b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="aa38b-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aa38b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aa38b-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="aa38b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa38b-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="aa38b-113">Remarks</span></span>

<span data-ttu-id="aa38b-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="aa38b-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```