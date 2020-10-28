---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mappad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730155"
---
# <a name="mapped-function"></a><span data-ttu-id="588d2-102">Mappad funktion</span><span class="sxs-lookup"><span data-stu-id="588d2-102">Mapped function</span></span>

<span data-ttu-id="588d2-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="588d2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="588d2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="588d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="588d2-105">Med tanke på en matris och en funktion som har definierats för elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.</span><span class="sxs-lookup"><span data-stu-id="588d2-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="588d2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="588d2-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="588d2-107">Mapper: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="588d2-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="588d2-108">En funktion från `'T` till `'U` som används för att mappa element.</span><span class="sxs-lookup"><span data-stu-id="588d2-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="588d2-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="588d2-109">array : 'T[]</span></span>

<span data-ttu-id="588d2-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="588d2-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="588d2-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="588d2-111">Output : 'U[]</span></span>

<span data-ttu-id="588d2-112">En matris `'U[]` med element som mappas av `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="588d2-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="588d2-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="588d2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="588d2-114">Inte</span><span class="sxs-lookup"><span data-stu-id="588d2-114">'T</span></span>

<span data-ttu-id="588d2-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="588d2-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="588d2-116">' U</span><span class="sxs-lookup"><span data-stu-id="588d2-116">'U</span></span>

<span data-ttu-id="588d2-117">Resultat typen för `mapper` funktionen.</span><span class="sxs-lookup"><span data-stu-id="588d2-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="588d2-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="588d2-118">Remarks</span></span>

<span data-ttu-id="588d2-119">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en funktion `mapper: 'T -> 'U` kan vi mappa element i matrisen och skapa en ny matris av typen `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="588d2-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>