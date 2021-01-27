---
uid: Microsoft.Quantum.Logical.And
title: Och-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849233"
---
# <a name="and-function"></a><span data-ttu-id="0cc89-102">Och-funktion</span><span class="sxs-lookup"><span data-stu-id="0cc89-102">And function</span></span>

<span data-ttu-id="0cc89-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0cc89-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0cc89-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cc89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cc89-105">Returnerar den booleska samningen av två värden.</span><span class="sxs-lookup"><span data-stu-id="0cc89-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="0cc89-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0cc89-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0cc89-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0cc89-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0cc89-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="0cc89-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="0cc89-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0cc89-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0cc89-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="0cc89-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0cc89-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0cc89-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0cc89-112">`true` om och endast om `a` och `b` är båda `true` .</span><span class="sxs-lookup"><span data-stu-id="0cc89-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0cc89-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0cc89-113">Remarks</span></span>

<span data-ttu-id="0cc89-114">Till skillnad från `and` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="0cc89-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="0cc89-115">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="0cc89-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```