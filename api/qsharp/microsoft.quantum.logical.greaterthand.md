---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Funktionen GreaterThanD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198035"
---
# <a name="greaterthand-function"></a><span data-ttu-id="b6af8-102">Funktionen GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="b6af8-102">GreaterThanD function</span></span>

<span data-ttu-id="b6af8-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b6af8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b6af8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6af8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6af8-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="b6af8-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b6af8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b6af8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b6af8-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6af8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6af8-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b6af8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b6af8-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6af8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6af8-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b6af8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b6af8-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b6af8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b6af8-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="b6af8-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6af8-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b6af8-113">Remarks</span></span>

<span data-ttu-id="b6af8-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b6af8-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```