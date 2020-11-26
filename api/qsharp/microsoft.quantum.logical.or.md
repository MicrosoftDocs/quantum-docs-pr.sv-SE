---
uid: Microsoft.Quantum.Logical.Or
title: Eller funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197134"
---
# <a name="or-function"></a><span data-ttu-id="ad9b3-102">Eller funktion</span><span class="sxs-lookup"><span data-stu-id="ad9b3-102">Or function</span></span>

<span data-ttu-id="ad9b3-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ad9b3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ad9b3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad9b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad9b3-105">Returnerar den booleska disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="ad9b3-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ad9b3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ad9b3-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="ad9b3-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad9b3-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad9b3-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="ad9b3-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="ad9b3-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad9b3-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad9b3-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="ad9b3-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ad9b3-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad9b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad9b3-112">`true` om och endast om antingen `a` eller `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="ad9b3-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad9b3-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ad9b3-113">Remarks</span></span>

<span data-ttu-id="ad9b3-114">Till skillnad från `or` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="ad9b3-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="ad9b3-115">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="ad9b3-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```