---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Funktionen LessThanOrEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726034"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="6f901-102">Funktionen LessThanOrEqualD</span><span class="sxs-lookup"><span data-stu-id="6f901-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="6f901-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6f901-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6f901-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f901-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f901-105">Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="6f901-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6f901-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6f901-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6f901-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f901-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f901-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6f901-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6f901-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f901-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f901-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="6f901-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6f901-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f901-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f901-112">`true` om och endast om `a` är mindre än eller lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="6f901-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f901-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6f901-113">Remarks</span></span>

<span data-ttu-id="6f901-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="6f901-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```