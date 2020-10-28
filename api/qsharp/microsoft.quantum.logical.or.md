---
uid: Microsoft.Quantum.Logical.Or
title: Eller funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730755"
---
# <a name="or-function"></a><span data-ttu-id="ff7df-102">Eller funktion</span><span class="sxs-lookup"><span data-stu-id="ff7df-102">Or function</span></span>

<span data-ttu-id="ff7df-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ff7df-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ff7df-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff7df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff7df-105">Returnerar den booleska disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="ff7df-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ff7df-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ff7df-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="ff7df-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff7df-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff7df-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="ff7df-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="ff7df-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff7df-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff7df-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="ff7df-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ff7df-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff7df-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff7df-112">`true` om och endast om antingen `a` eller `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="ff7df-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff7df-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ff7df-113">Remarks</span></span>

<span data-ttu-id="ff7df-114">Till skillnad från `or` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="ff7df-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="ff7df-115">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="ff7df-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```