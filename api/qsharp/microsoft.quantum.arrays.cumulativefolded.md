---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Funktionen CumulativeFolded
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730366"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="23379-102">Funktionen CumulativeFolded</span><span class="sxs-lookup"><span data-stu-id="23379-102">CumulativeFolded function</span></span>

<span data-ttu-id="23379-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23379-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23379-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23379-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23379-105">Kombinerar mappad och vikning till en enda funktion</span><span class="sxs-lookup"><span data-stu-id="23379-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="23379-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="23379-106">Description</span></span>

<span data-ttu-id="23379-107">Den här funktionen upprepar `fn` funktionen genom matrisen, med början från ett initialt tillstånd `state` och returnerar alla mellanliggande värden, inte inklusive det ursprungliga läget.</span><span class="sxs-lookup"><span data-stu-id="23379-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="23379-108">Indata</span><span class="sxs-lookup"><span data-stu-id="23379-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="23379-109">FN: (' State, s)-> ' status</span><span class="sxs-lookup"><span data-stu-id="23379-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="23379-110">En funktion som ska vikas över matrisen</span><span class="sxs-lookup"><span data-stu-id="23379-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="23379-111">tillstånd: status</span><span class="sxs-lookup"><span data-stu-id="23379-111">state : 'State</span></span>

<span data-ttu-id="23379-112">Initialt tillstånd att vikas</span><span class="sxs-lookup"><span data-stu-id="23379-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="23379-113">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="23379-113">array : 'T[]</span></span>

<span data-ttu-id="23379-114">En matris med värden som ska vikas</span><span class="sxs-lookup"><span data-stu-id="23379-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="23379-115">Utdata: "State []</span><span class="sxs-lookup"><span data-stu-id="23379-115">Output : 'State[]</span></span>

<span data-ttu-id="23379-116">Alla mellanliggande tillstånd, inklusive det slutliga tillståndet, men inte det ursprungliga tillståndet.</span><span class="sxs-lookup"><span data-stu-id="23379-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="23379-117">Längden på den utgående matrisen har samma längd som `array` .</span><span class="sxs-lookup"><span data-stu-id="23379-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23379-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="23379-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="23379-119">Status</span><span class="sxs-lookup"><span data-stu-id="23379-119">'State</span></span>

<span data-ttu-id="23379-120">Den typ av tillstånd som `fn` funktionen körs på, dvs accepterar som första inmatade och returnerade.</span><span class="sxs-lookup"><span data-stu-id="23379-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="23379-121">Inte</span><span class="sxs-lookup"><span data-stu-id="23379-121">'T</span></span>

<span data-ttu-id="23379-122">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="23379-122">The type of `array` elements.</span></span>