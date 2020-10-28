---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Funktionen NotEqualB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725986"
---
# <a name="notequalb-function"></a><span data-ttu-id="4d4f0-102">Funktionen NotEqualB</span><span class="sxs-lookup"><span data-stu-id="4d4f0-102">NotEqualB function</span></span>

<span data-ttu-id="4d4f0-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4d4f0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d4f0-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="4d4f0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4d4f0-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="4d4f0-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d4f0-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="4d4f0-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d4f0-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4d4f0-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d4f0-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="4d4f0-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d4f0-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4d4f0-113">Remarks</span></span>

<span data-ttu-id="4d4f0-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="4d4f0-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```