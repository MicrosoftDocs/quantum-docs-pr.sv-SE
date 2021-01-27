---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Funktionen NotEqualB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814414"
---
# <a name="notequalb-function"></a><span data-ttu-id="b8a4f-102">Funktionen NotEqualB</span><span class="sxs-lookup"><span data-stu-id="b8a4f-102">NotEqualB function</span></span>

<span data-ttu-id="b8a4f-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b8a4f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b8a4f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8a4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8a4f-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="b8a4f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="b8a4f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b8a4f-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="b8a4f-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b8a4f-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b8a4f-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b8a4f-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="b8a4f-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b8a4f-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b8a4f-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b8a4f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b8a4f-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b8a4f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b8a4f-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="b8a4f-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8a4f-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b8a4f-113">Remarks</span></span>

<span data-ttu-id="b8a4f-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b8a4f-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```