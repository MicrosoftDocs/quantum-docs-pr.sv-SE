---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: Funktionen NearlyEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814374"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="df622-102">Funktionen NearlyEqualD</span><span class="sxs-lookup"><span data-stu-id="df622-102">NearlyEqualD function</span></span>

<span data-ttu-id="df622-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="df622-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="df622-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df622-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df622-105">Returnerar true om och bara om två indata är nästan identiska (det vill säga inom en tolerans på 1e-12).</span><span class="sxs-lookup"><span data-stu-id="df622-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="df622-106">Indata</span><span class="sxs-lookup"><span data-stu-id="df622-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="df622-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df622-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df622-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="df622-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="df622-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df622-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df622-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="df622-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="df622-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df622-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df622-112">`true` om och bara om `a` är nästan lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="df622-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="df622-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="df622-113">Remarks</span></span>

<span data-ttu-id="df622-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="df622-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```