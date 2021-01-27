---
uid: Microsoft.Quantum.Logical.Or
title: Eller funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848469"
---
# <a name="or-function"></a><span data-ttu-id="2e4a2-102">Eller funktion</span><span class="sxs-lookup"><span data-stu-id="2e4a2-102">Or function</span></span>

<span data-ttu-id="2e4a2-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2e4a2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2e4a2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e4a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e4a2-105">Returnerar den booleska disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="2e4a2-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="2e4a2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2e4a2-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="2e4a2-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e4a2-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e4a2-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="2e4a2-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="2e4a2-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e4a2-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e4a2-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="2e4a2-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2e4a2-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e4a2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e4a2-112">`true` om och endast om antingen `a` eller `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="2e4a2-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e4a2-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2e4a2-113">Remarks</span></span>

<span data-ttu-id="2e4a2-114">Till skillnad från `or` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="2e4a2-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="2e4a2-115">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="2e4a2-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```