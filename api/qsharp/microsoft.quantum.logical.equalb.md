---
uid: Microsoft.Quantum.Logical.EqualB
title: Funktionen EqualB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198477"
---
# <a name="equalb-function"></a><span data-ttu-id="8091c-102">Funktionen EqualB</span><span class="sxs-lookup"><span data-stu-id="8091c-102">EqualB function</span></span>

<span data-ttu-id="8091c-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8091c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8091c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8091c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8091c-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="8091c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="8091c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8091c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="8091c-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8091c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8091c-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8091c-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="8091c-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8091c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8091c-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8091c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8091c-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8091c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8091c-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="8091c-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8091c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8091c-113">Remarks</span></span>

<span data-ttu-id="8091c-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="8091c-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```