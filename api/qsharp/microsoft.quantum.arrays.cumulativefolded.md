---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Funktionen CumulativeFolded
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210037"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="8c001-102">Funktionen CumulativeFolded</span><span class="sxs-lookup"><span data-stu-id="8c001-102">CumulativeFolded function</span></span>

<span data-ttu-id="8c001-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8c001-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8c001-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c001-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c001-105">Kombinerar mappad och vikning till en enda funktion</span><span class="sxs-lookup"><span data-stu-id="8c001-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="8c001-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c001-106">Description</span></span>

<span data-ttu-id="8c001-107">Den här funktionen upprepar `fn` funktionen genom matrisen, med början från ett initialt tillstånd `state` och returnerar alla mellanliggande värden, inte inklusive det ursprungliga läget.</span><span class="sxs-lookup"><span data-stu-id="8c001-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="8c001-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8c001-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="8c001-109">FN: (' State, s)-> ' status</span><span class="sxs-lookup"><span data-stu-id="8c001-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="8c001-110">En funktion som ska vikas över matrisen</span><span class="sxs-lookup"><span data-stu-id="8c001-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="8c001-111">tillstånd: status</span><span class="sxs-lookup"><span data-stu-id="8c001-111">state : 'State</span></span>

<span data-ttu-id="8c001-112">Initialt tillstånd att vikas</span><span class="sxs-lookup"><span data-stu-id="8c001-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="8c001-113">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="8c001-113">array : 'T[]</span></span>

<span data-ttu-id="8c001-114">En matris med värden som ska vikas</span><span class="sxs-lookup"><span data-stu-id="8c001-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="8c001-115">Utdata: "State []</span><span class="sxs-lookup"><span data-stu-id="8c001-115">Output : 'State[]</span></span>

<span data-ttu-id="8c001-116">Alla mellanliggande tillstånd, inklusive det slutliga tillståndet, men inte det ursprungliga tillståndet.</span><span class="sxs-lookup"><span data-stu-id="8c001-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="8c001-117">Längden på den utgående matrisen har samma längd som `array` .</span><span class="sxs-lookup"><span data-stu-id="8c001-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8c001-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8c001-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="8c001-119">Status</span><span class="sxs-lookup"><span data-stu-id="8c001-119">'State</span></span>

<span data-ttu-id="8c001-120">Den typ av tillstånd som `fn` funktionen körs på, dvs accepterar som första inmatade och returnerade.</span><span class="sxs-lookup"><span data-stu-id="8c001-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="8c001-121">Inte</span><span class="sxs-lookup"><span data-stu-id="8c001-121">'T</span></span>

<span data-ttu-id="8c001-122">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="8c001-122">The type of `array` elements.</span></span>