---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Funktionen NotNearlyEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731254"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="c4a29-102">Funktionen NotNearlyEqualD</span><span class="sxs-lookup"><span data-stu-id="c4a29-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="c4a29-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c4a29-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c4a29-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4a29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4a29-105">Returnerar true om och endast om två indata inte är nästan identiska (dvs. inte är inom toleransen för 1e-12).</span><span class="sxs-lookup"><span data-stu-id="c4a29-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c4a29-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c4a29-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c4a29-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4a29-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4a29-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="c4a29-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c4a29-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4a29-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4a29-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="c4a29-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c4a29-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4a29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4a29-112">`true` om och endast om `a` är inte nästan lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="c4a29-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4a29-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c4a29-113">Remarks</span></span>

<span data-ttu-id="c4a29-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="c4a29-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```