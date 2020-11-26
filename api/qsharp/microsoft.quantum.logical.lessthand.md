---
uid: Microsoft.Quantum.Logical.LessThanD
title: Funktionen LessThanD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197746"
---
# <a name="lessthand-function"></a><span data-ttu-id="3bcfd-102">Funktionen LessThanD</span><span class="sxs-lookup"><span data-stu-id="3bcfd-102">LessThanD function</span></span>

<span data-ttu-id="3bcfd-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3bcfd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3bcfd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bcfd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bcfd-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="3bcfd-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3bcfd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3bcfd-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3bcfd-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3bcfd-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3bcfd-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3bcfd-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3bcfd-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3bcfd-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3bcfd-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3bcfd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3bcfd-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3bcfd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3bcfd-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="3bcfd-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bcfd-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3bcfd-113">Remarks</span></span>

<span data-ttu-id="3bcfd-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="3bcfd-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```