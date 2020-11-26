---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Funktionen MappedByIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209935"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="a9278-102">Funktionen MappedByIndex</span><span class="sxs-lookup"><span data-stu-id="a9278-102">MappedByIndex function</span></span>

<span data-ttu-id="a9278-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a9278-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a9278-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9278-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9278-105">Med tanke på en matris och en funktion som har definierats för de indexerade elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9278-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a9278-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a9278-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="a9278-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="a9278-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="a9278-108">En funktion från `(Int, 'T)` till `'U` som används för att mappa element och deras index.</span><span class="sxs-lookup"><span data-stu-id="a9278-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="a9278-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="a9278-109">array : 'T[]</span></span>

<span data-ttu-id="a9278-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="a9278-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a9278-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="a9278-111">Output : 'U[]</span></span>

<span data-ttu-id="a9278-112">En matris `'U[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9278-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a9278-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a9278-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9278-114">Inte</span><span class="sxs-lookup"><span data-stu-id="a9278-114">'T</span></span>

<span data-ttu-id="a9278-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="a9278-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a9278-116">' U</span><span class="sxs-lookup"><span data-stu-id="a9278-116">'U</span></span>

<span data-ttu-id="a9278-117">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9278-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9278-118">Se även</span><span class="sxs-lookup"><span data-stu-id="a9278-118">See Also</span></span>

- [<span data-ttu-id="a9278-119">Microsoft. Quantum. arrayer. mappas</span><span class="sxs-lookup"><span data-stu-id="a9278-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)