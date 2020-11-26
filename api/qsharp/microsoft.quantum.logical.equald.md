---
uid: Microsoft.Quantum.Logical.EqualD
title: Likhets funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198154"
---
# <a name="equald-function"></a><span data-ttu-id="3f8a9-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="3f8a9-102">EqualD function</span></span>

<span data-ttu-id="3f8a9-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3f8a9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3f8a9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f8a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f8a9-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3f8a9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3f8a9-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3f8a9-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f8a9-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f8a9-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3f8a9-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f8a9-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f8a9-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3f8a9-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3f8a9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3f8a9-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="3f8a9-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f8a9-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3f8a9-113">Remarks</span></span>

<span data-ttu-id="3f8a9-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="3f8a9-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```