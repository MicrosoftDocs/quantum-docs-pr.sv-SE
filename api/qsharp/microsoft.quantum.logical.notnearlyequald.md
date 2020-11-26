---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Funktionen NotNearlyEqualD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 23229b1630982eba4485330cc2290aed733c4d86
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197151"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="e6409-102">Funktionen NotNearlyEqualD</span><span class="sxs-lookup"><span data-stu-id="e6409-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="e6409-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e6409-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e6409-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6409-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6409-105">Returnerar true om och endast om två indata inte är nästan identiska (dvs. inte är inom toleransen för 1e-12).</span><span class="sxs-lookup"><span data-stu-id="e6409-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e6409-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e6409-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e6409-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6409-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6409-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e6409-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e6409-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6409-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6409-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e6409-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e6409-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e6409-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e6409-112">`true` om och endast om `a` är inte nästan lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="e6409-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6409-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e6409-113">Remarks</span></span>

<span data-ttu-id="e6409-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="e6409-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```