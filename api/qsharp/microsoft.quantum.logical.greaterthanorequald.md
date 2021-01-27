---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: Funktionen GreaterThanOrEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 98fa55c249f2ade414254d1bccda46a8602b828c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815868"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="7ffbf-102">Funktionen GreaterThanOrEqualD</span><span class="sxs-lookup"><span data-stu-id="7ffbf-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="7ffbf-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7ffbf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7ffbf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ffbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ffbf-105">Returnerar true om och endast om ett tal är större än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="7ffbf-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7ffbf-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7ffbf-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7ffbf-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ffbf-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ffbf-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7ffbf-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7ffbf-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ffbf-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ffbf-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7ffbf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7ffbf-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7ffbf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7ffbf-112">`true` om och bara om `a` är större än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="7ffbf-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ffbf-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7ffbf-113">Remarks</span></span>

<span data-ttu-id="7ffbf-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="7ffbf-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```