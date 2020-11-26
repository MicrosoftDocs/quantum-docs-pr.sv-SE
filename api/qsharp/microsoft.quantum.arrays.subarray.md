---
uid: Microsoft.Quantum.Arrays.Subarray
title: Under mat ris funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220169"
---
# <a name="subarray-function"></a><span data-ttu-id="d0a7f-102">Under mat ris funktion</span><span class="sxs-lookup"><span data-stu-id="d0a7f-102">Subarray function</span></span>

<span data-ttu-id="d0a7f-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0a7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0a7f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0a7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0a7f-105">Tar en matris och en lista med platser och skapar en ny matris som är utformad från elementen i den ursprungliga matrisen som matchar de tilldelade platserna.</span><span class="sxs-lookup"><span data-stu-id="d0a7f-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d0a7f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d0a7f-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="d0a7f-107">index: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d0a7f-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d0a7f-108">En lista med heltal som används för att definiera undermatrisen.</span><span class="sxs-lookup"><span data-stu-id="d0a7f-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="d0a7f-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="d0a7f-109">array : 'T[]</span></span>

<span data-ttu-id="d0a7f-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="d0a7f-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0a7f-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="d0a7f-111">Output : 'T[]</span></span>

<span data-ttu-id="d0a7f-112">En matris `out` med element vars index motsvarar undermatrisen, t `out[idx] == array[indices[idx]]` . ex..</span><span class="sxs-lookup"><span data-stu-id="d0a7f-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0a7f-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d0a7f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0a7f-114">Inte</span><span class="sxs-lookup"><span data-stu-id="d0a7f-114">'T</span></span>

<span data-ttu-id="d0a7f-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="d0a7f-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0a7f-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d0a7f-116">Remarks</span></span>

<span data-ttu-id="d0a7f-117">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en lista över platser som `Int[]` definierar undermatrisen.</span><span class="sxs-lookup"><span data-stu-id="d0a7f-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="d0a7f-118">Undermatrisens konstruktion är en baserad på att skapa en ny, djupgående kopia av den aktuella matrisen i stället för att behålla referenser.</span><span class="sxs-lookup"><span data-stu-id="d0a7f-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="d0a7f-119">Om `Length(indices) < Length(array)` den här funktionen kommer att returnera en delmängd av `array` .</span><span class="sxs-lookup"><span data-stu-id="d0a7f-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="d0a7f-120">Å andra sidan `indices` upprepas motsvarande element i även om de innehåller upprepade element `array` .</span><span class="sxs-lookup"><span data-stu-id="d0a7f-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="d0a7f-121">Om `indices` och `array` har samma längd tillhandahåller den här funktionen permutationer av `array` .</span><span class="sxs-lookup"><span data-stu-id="d0a7f-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>