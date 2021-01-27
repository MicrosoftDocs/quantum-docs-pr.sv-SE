---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Funktionen NotNearlyEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848490"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="46320-102">Funktionen NotNearlyEqualD</span><span class="sxs-lookup"><span data-stu-id="46320-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="46320-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="46320-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="46320-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46320-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46320-105">Returnerar true om och endast om två indata inte är nästan identiska (dvs. inte är inom toleransen för 1e-12).</span><span class="sxs-lookup"><span data-stu-id="46320-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="46320-106">Indata</span><span class="sxs-lookup"><span data-stu-id="46320-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="46320-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46320-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46320-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="46320-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="46320-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46320-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46320-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="46320-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="46320-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46320-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46320-112">`true` om och endast om `a` är inte nästan lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="46320-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="46320-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="46320-113">Remarks</span></span>

<span data-ttu-id="46320-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="46320-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```