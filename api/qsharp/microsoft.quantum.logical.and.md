---
uid: Microsoft.Quantum.Logical.And
title: Och-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731302"
---
# <a name="and-function"></a><span data-ttu-id="afe35-102">Och-funktion</span><span class="sxs-lookup"><span data-stu-id="afe35-102">And function</span></span>

<span data-ttu-id="afe35-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="afe35-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="afe35-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afe35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afe35-105">Returnerar den booleska samningen av två värden.</span><span class="sxs-lookup"><span data-stu-id="afe35-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="afe35-106">Indata</span><span class="sxs-lookup"><span data-stu-id="afe35-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="afe35-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="afe35-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="afe35-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="afe35-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="afe35-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="afe35-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="afe35-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="afe35-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="afe35-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="afe35-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="afe35-112">`true` om och endast om `a` och `b` är båda `true` .</span><span class="sxs-lookup"><span data-stu-id="afe35-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="afe35-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="afe35-113">Remarks</span></span>

<span data-ttu-id="afe35-114">Till skillnad från `and` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="afe35-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="afe35-115">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="afe35-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```