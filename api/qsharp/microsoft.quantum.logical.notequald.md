---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Funktionen NotEqualD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197253"
---
# <a name="notequald-function"></a><span data-ttu-id="a2f93-102">Funktionen NotEqualD</span><span class="sxs-lookup"><span data-stu-id="a2f93-102">NotEqualD function</span></span>

<span data-ttu-id="a2f93-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a2f93-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a2f93-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2f93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2f93-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="a2f93-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="a2f93-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a2f93-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="a2f93-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a2f93-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a2f93-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a2f93-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="a2f93-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a2f93-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a2f93-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a2f93-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a2f93-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a2f93-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a2f93-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="a2f93-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2f93-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a2f93-113">Remarks</span></span>

<span data-ttu-id="a2f93-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a2f93-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```