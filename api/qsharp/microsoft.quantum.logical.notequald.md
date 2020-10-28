---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Funktionen NotEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732918"
---
# <a name="notequald-function"></a><span data-ttu-id="621e5-102">Funktionen NotEqualD</span><span class="sxs-lookup"><span data-stu-id="621e5-102">NotEqualD function</span></span>

<span data-ttu-id="621e5-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="621e5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="621e5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="621e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="621e5-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="621e5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="621e5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="621e5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="621e5-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="621e5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="621e5-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="621e5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="621e5-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="621e5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="621e5-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="621e5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="621e5-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="621e5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="621e5-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="621e5-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="621e5-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="621e5-113">Remarks</span></span>

<span data-ttu-id="621e5-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="621e5-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```