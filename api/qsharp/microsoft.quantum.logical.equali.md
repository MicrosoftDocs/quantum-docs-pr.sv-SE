---
uid: Microsoft.Quantum.Logical.EqualI
title: Likhets funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726079"
---
# <a name="equali-function"></a><span data-ttu-id="a078c-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="a078c-102">EqualI function</span></span>

<span data-ttu-id="a078c-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a078c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a078c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a078c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a078c-105">Returnerar true om och bara om två indata är lika.</span><span class="sxs-lookup"><span data-stu-id="a078c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a078c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a078c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a078c-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a078c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a078c-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a078c-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a078c-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a078c-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a078c-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a078c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a078c-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a078c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a078c-112">`true` om och bara om `a` är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="a078c-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a078c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a078c-113">Remarks</span></span>

<span data-ttu-id="a078c-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a078c-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```