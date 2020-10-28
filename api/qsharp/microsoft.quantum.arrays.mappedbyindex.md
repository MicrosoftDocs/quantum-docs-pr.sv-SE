---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Funktionen MappedByIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730139"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="6ffe5-102">Funktionen MappedByIndex</span><span class="sxs-lookup"><span data-stu-id="6ffe5-102">MappedByIndex function</span></span>

<span data-ttu-id="6ffe5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6ffe5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6ffe5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ffe5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ffe5-105">Med tanke på en matris och en funktion som har definierats för de indexerade elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.</span><span class="sxs-lookup"><span data-stu-id="6ffe5-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="6ffe5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6ffe5-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="6ffe5-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="6ffe5-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="6ffe5-108">En funktion från `(Int, 'T)` till `'U` som används för att mappa element och deras index.</span><span class="sxs-lookup"><span data-stu-id="6ffe5-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="6ffe5-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="6ffe5-109">array : 'T[]</span></span>

<span data-ttu-id="6ffe5-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="6ffe5-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="6ffe5-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="6ffe5-111">Output : 'U[]</span></span>

<span data-ttu-id="6ffe5-112">En matris `'U[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="6ffe5-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6ffe5-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6ffe5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ffe5-114">Inte</span><span class="sxs-lookup"><span data-stu-id="6ffe5-114">'T</span></span>

<span data-ttu-id="6ffe5-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="6ffe5-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="6ffe5-116">' U</span><span class="sxs-lookup"><span data-stu-id="6ffe5-116">'U</span></span>

<span data-ttu-id="6ffe5-117">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="6ffe5-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ffe5-118">Se även</span><span class="sxs-lookup"><span data-stu-id="6ffe5-118">See Also</span></span>

- [<span data-ttu-id="6ffe5-119">Microsoft. Quantum. arrayer. mappas</span><span class="sxs-lookup"><span data-stu-id="6ffe5-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)