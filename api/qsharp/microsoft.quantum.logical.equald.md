---
uid: Microsoft.Quantum.Logical.EqualD
title: Likhets funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816873"
---
# <a name="equald-function"></a><span data-ttu-id="94deb-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="94deb-102">EqualD function</span></span>

<span data-ttu-id="94deb-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="94deb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="94deb-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94deb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94deb-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="94deb-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="94deb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="94deb-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="94deb-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94deb-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="94deb-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="94deb-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="94deb-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94deb-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="94deb-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="94deb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="94deb-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94deb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94deb-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="94deb-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="94deb-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="94deb-113">Remarks</span></span>

<span data-ttu-id="94deb-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="94deb-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```