---
uid: Microsoft.Quantum.Logical.LessThanI
title: Funktionen LessThanI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815824"
---
# <a name="lessthani-function"></a><span data-ttu-id="02141-102">Funktionen LessThanI</span><span class="sxs-lookup"><span data-stu-id="02141-102">LessThanI function</span></span>

<span data-ttu-id="02141-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="02141-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="02141-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02141-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02141-105">Returnerar true om och endast om ett tal är mindre än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="02141-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="02141-106">Indata</span><span class="sxs-lookup"><span data-stu-id="02141-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="02141-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02141-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="02141-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="02141-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="02141-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02141-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="02141-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="02141-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="02141-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02141-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="02141-112">`true` om och bara om `a` är strikt mindre än `b` .</span><span class="sxs-lookup"><span data-stu-id="02141-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="02141-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="02141-113">Remarks</span></span>

<span data-ttu-id="02141-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="02141-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```