---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Funktionen MappedOverRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845642"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="5806c-102">Funktionen MappedOverRange</span><span class="sxs-lookup"><span data-stu-id="5806c-102">MappedOverRange function</span></span>

<span data-ttu-id="5806c-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5806c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5806c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5806c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5806c-105">Med ett intervall och en funktion som tar ett heltal som inmatat, returnerar en ny matris som består av avbildningarna av värdena i intervallet under funktionen.</span><span class="sxs-lookup"><span data-stu-id="5806c-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5806c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5806c-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="5806c-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="5806c-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="5806c-108">En funktion från `Int` till `'T` som används för att mappa intervall värden.</span><span class="sxs-lookup"><span data-stu-id="5806c-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="5806c-109">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="5806c-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="5806c-110">Ett heltals intervall.</span><span class="sxs-lookup"><span data-stu-id="5806c-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="5806c-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="5806c-111">Output : 'T[]</span></span>

<span data-ttu-id="5806c-112">En matris `'T[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="5806c-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5806c-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5806c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5806c-114">Inte</span><span class="sxs-lookup"><span data-stu-id="5806c-114">'T</span></span>

<span data-ttu-id="5806c-115">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="5806c-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="5806c-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="5806c-116">Example</span></span>

<span data-ttu-id="5806c-117">I det här exemplet läggs 1 till i ett intervall med jämna tal:</span><span class="sxs-lookup"><span data-stu-id="5806c-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="5806c-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5806c-118">Remarks</span></span>

<span data-ttu-id="5806c-119">Funktionen definieras för generiska typer, d.v.s. När vi har en funktion `mapper: Int -> 'T` kan vi mappa värdena i intervallet och skapa en matris av typen `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="5806c-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5806c-120">Se även</span><span class="sxs-lookup"><span data-stu-id="5806c-120">See Also</span></span>

- [<span data-ttu-id="5806c-121">Microsoft. Quantum. arrayer. mappas</span><span class="sxs-lookup"><span data-stu-id="5806c-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)