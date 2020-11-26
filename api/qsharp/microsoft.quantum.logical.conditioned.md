---
uid: Microsoft.Quantum.Logical.Conditioned
title: Conditionisk funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198494"
---
# <a name="conditioned-function"></a><span data-ttu-id="44928-102">Conditionisk funktion</span><span class="sxs-lookup"><span data-stu-id="44928-102">Conditioned function</span></span>

<span data-ttu-id="44928-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="44928-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="44928-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44928-105">Returnerar ett av två värden, beroende på värdet för ett booleskt villkor.</span><span class="sxs-lookup"><span data-stu-id="44928-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="44928-106">Indata</span><span class="sxs-lookup"><span data-stu-id="44928-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="44928-107">villkor: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="44928-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="44928-108">Ett villkor som används för att styra vilka indatatyper som returneras.</span><span class="sxs-lookup"><span data-stu-id="44928-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="44928-109">ifTrue: ' t</span><span class="sxs-lookup"><span data-stu-id="44928-109">ifTrue : 'T</span></span>

<span data-ttu-id="44928-110">Värdet som ska returneras när `condition` är `true` .</span><span class="sxs-lookup"><span data-stu-id="44928-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="44928-111">ifFalse: ' t</span><span class="sxs-lookup"><span data-stu-id="44928-111">ifFalse : 'T</span></span>

<span data-ttu-id="44928-112">Värdet som ska returneras när `condition` är `false` .</span><span class="sxs-lookup"><span data-stu-id="44928-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="44928-113">Utdata: ' t</span><span class="sxs-lookup"><span data-stu-id="44928-113">Output : 'T</span></span>

<span data-ttu-id="44928-114">`ifTrue` Om `condition` är `true` , och `ifFalse` annars.</span><span class="sxs-lookup"><span data-stu-id="44928-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="44928-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="44928-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44928-116">Inte</span><span class="sxs-lookup"><span data-stu-id="44928-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="44928-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="44928-117">Remarks</span></span>

<span data-ttu-id="44928-118">Till skillnad från `?|` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="44928-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="44928-119">Till följd av kort slutning är följande motsvarigheter:</span><span class="sxs-lookup"><span data-stu-id="44928-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```