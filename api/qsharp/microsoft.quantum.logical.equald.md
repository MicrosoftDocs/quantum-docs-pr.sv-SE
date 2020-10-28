---
uid: Microsoft.Quantum.Logical.EqualD
title: Likhets funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726655"
---
# <a name="equald-function"></a><span data-ttu-id="3cd37-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="3cd37-102">EqualD function</span></span>

<span data-ttu-id="3cd37-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3cd37-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3cd37-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3cd37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3cd37-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="3cd37-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3cd37-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3cd37-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3cd37-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3cd37-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3cd37-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3cd37-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3cd37-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3cd37-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3cd37-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3cd37-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3cd37-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3cd37-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3cd37-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="3cd37-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cd37-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3cd37-113">Remarks</span></span>

<span data-ttu-id="3cd37-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="3cd37-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```