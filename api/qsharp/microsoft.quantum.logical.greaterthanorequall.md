---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: Funktionen GreaterThanOrEqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732443"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="e1fd7-102">Funktionen GreaterThanOrEqualL</span><span class="sxs-lookup"><span data-stu-id="e1fd7-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="e1fd7-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e1fd7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e1fd7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1fd7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1fd7-105">Returnerar true om och endast om ett tal är större än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="e1fd7-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e1fd7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e1fd7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e1fd7-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e1fd7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e1fd7-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e1fd7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e1fd7-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e1fd7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e1fd7-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e1fd7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e1fd7-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e1fd7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e1fd7-112">`true` om och bara om `a` är större än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="e1fd7-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1fd7-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e1fd7-113">Remarks</span></span>

<span data-ttu-id="e1fd7-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="e1fd7-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```