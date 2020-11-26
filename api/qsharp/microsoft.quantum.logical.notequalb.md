---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Funktionen NotEqualB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197389"
---
# <a name="notequalb-function"></a><span data-ttu-id="86141-102">Funktionen NotEqualB</span><span class="sxs-lookup"><span data-stu-id="86141-102">NotEqualB function</span></span>

<span data-ttu-id="86141-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="86141-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="86141-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86141-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86141-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="86141-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="86141-106">Indata</span><span class="sxs-lookup"><span data-stu-id="86141-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="86141-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="86141-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="86141-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="86141-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="86141-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="86141-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="86141-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="86141-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="86141-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="86141-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="86141-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="86141-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="86141-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="86141-113">Remarks</span></span>

<span data-ttu-id="86141-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="86141-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```