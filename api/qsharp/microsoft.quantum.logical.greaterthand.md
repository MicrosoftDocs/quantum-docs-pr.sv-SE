---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Funktionen GreaterThanD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726058"
---
# <a name="greaterthand-function"></a><span data-ttu-id="ba9de-102">Funktionen GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="ba9de-102">GreaterThanD function</span></span>

<span data-ttu-id="ba9de-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ba9de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ba9de-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba9de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba9de-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="ba9de-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ba9de-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ba9de-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ba9de-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba9de-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba9de-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="ba9de-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ba9de-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba9de-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba9de-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="ba9de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ba9de-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ba9de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ba9de-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="ba9de-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba9de-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ba9de-113">Remarks</span></span>

<span data-ttu-id="ba9de-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="ba9de-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```