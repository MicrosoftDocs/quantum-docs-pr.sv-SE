---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Funktionen MappedByIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845672"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="f126a-102">Funktionen MappedByIndex</span><span class="sxs-lookup"><span data-stu-id="f126a-102">MappedByIndex function</span></span>

<span data-ttu-id="f126a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f126a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f126a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f126a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f126a-105">Med tanke på en matris och en funktion som har definierats för de indexerade elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.</span><span class="sxs-lookup"><span data-stu-id="f126a-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="f126a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f126a-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="f126a-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="f126a-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="f126a-108">En funktion från `(Int, 'T)` till `'U` som används för att mappa element och deras index.</span><span class="sxs-lookup"><span data-stu-id="f126a-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="f126a-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="f126a-109">array : 'T[]</span></span>

<span data-ttu-id="f126a-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="f126a-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="f126a-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="f126a-111">Output : 'U[]</span></span>

<span data-ttu-id="f126a-112">En matris `'U[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="f126a-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f126a-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f126a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f126a-114">Inte</span><span class="sxs-lookup"><span data-stu-id="f126a-114">'T</span></span>

<span data-ttu-id="f126a-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="f126a-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="f126a-116">' U</span><span class="sxs-lookup"><span data-stu-id="f126a-116">'U</span></span>

<span data-ttu-id="f126a-117">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="f126a-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="f126a-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="f126a-118">Example</span></span>

<span data-ttu-id="f126a-119">Följande två rader är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="f126a-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="f126a-120">och</span><span class="sxs-lookup"><span data-stu-id="f126a-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="f126a-121">Se även</span><span class="sxs-lookup"><span data-stu-id="f126a-121">See Also</span></span>

- [<span data-ttu-id="f126a-122">Microsoft. Quantum. arrayer. mappas</span><span class="sxs-lookup"><span data-stu-id="f126a-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)