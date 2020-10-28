---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Funktionen MappedOverRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730131"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="ee3ed-102">Funktionen MappedOverRange</span><span class="sxs-lookup"><span data-stu-id="ee3ed-102">MappedOverRange function</span></span>

<span data-ttu-id="ee3ed-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ee3ed-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ee3ed-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee3ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee3ed-105">Med ett intervall och en funktion som tar ett heltal som inmatat, returnerar en ny matris som består av avbildningarna av värdena i intervallet under funktionen.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ee3ed-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ee3ed-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="ee3ed-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="ee3ed-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="ee3ed-108">En funktion från `Int` till `'T` som används för att mappa intervall värden.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="ee3ed-109">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ee3ed-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ee3ed-110">Ett heltals intervall.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="ee3ed-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="ee3ed-111">Output : 'T[]</span></span>

<span data-ttu-id="ee3ed-112">En matris `'T[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ee3ed-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ee3ed-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee3ed-114">Inte</span><span class="sxs-lookup"><span data-stu-id="ee3ed-114">'T</span></span>

<span data-ttu-id="ee3ed-115">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee3ed-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ee3ed-116">Remarks</span></span>

<span data-ttu-id="ee3ed-117">Funktionen definieras för generiska typer, d.v.s. När vi har en funktion `mapper: Int -> 'T` kan vi mappa värdena i intervallet och skapa en matris av typen `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="ee3ed-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee3ed-118">Se även</span><span class="sxs-lookup"><span data-stu-id="ee3ed-118">See Also</span></span>

- [<span data-ttu-id="ee3ed-119">Microsoft. Quantum. arrayer. mappas</span><span class="sxs-lookup"><span data-stu-id="ee3ed-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)