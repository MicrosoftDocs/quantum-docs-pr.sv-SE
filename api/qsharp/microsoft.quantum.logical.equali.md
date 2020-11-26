---
uid: Microsoft.Quantum.Logical.EqualI
title: Likhets funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198171"
---
# <a name="equali-function"></a><span data-ttu-id="d0230-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="d0230-102">EqualI function</span></span>

<span data-ttu-id="d0230-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d0230-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d0230-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0230-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0230-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="d0230-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="d0230-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d0230-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d0230-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0230-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0230-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="d0230-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="d0230-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0230-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0230-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="d0230-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d0230-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0230-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d0230-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="d0230-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0230-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d0230-113">Remarks</span></span>

<span data-ttu-id="d0230-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="d0230-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```