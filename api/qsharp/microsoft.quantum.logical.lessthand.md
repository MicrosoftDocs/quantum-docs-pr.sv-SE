---
uid: Microsoft.Quantum.Logical.LessThanD
title: Funktionen LessThanD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732926"
---
# <a name="lessthand-function"></a><span data-ttu-id="6db78-102">Funktionen LessThanD</span><span class="sxs-lookup"><span data-stu-id="6db78-102">LessThanD function</span></span>

<span data-ttu-id="6db78-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6db78-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6db78-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6db78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6db78-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="6db78-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6db78-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6db78-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6db78-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6db78-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6db78-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6db78-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6db78-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6db78-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6db78-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6db78-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6db78-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6db78-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6db78-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="6db78-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6db78-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6db78-113">Remarks</span></span>

<span data-ttu-id="6db78-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="6db78-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```