---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: Funktionen NearlyEqualD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197474"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="f9278-102">Funktionen NearlyEqualD</span><span class="sxs-lookup"><span data-stu-id="f9278-102">NearlyEqualD function</span></span>

<span data-ttu-id="f9278-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f9278-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f9278-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9278-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9278-105">Returnerar true om och bara om två indata är nästan identiska (det vill säga inom en tolerans på 1e-12).</span><span class="sxs-lookup"><span data-stu-id="f9278-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f9278-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f9278-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f9278-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9278-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9278-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="f9278-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f9278-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9278-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9278-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="f9278-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f9278-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9278-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9278-112">`true` om och bara om `a` är nästan lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="f9278-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9278-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f9278-113">Remarks</span></span>

<span data-ttu-id="f9278-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="f9278-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```