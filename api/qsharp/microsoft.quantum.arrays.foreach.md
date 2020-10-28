---
uid: Microsoft.Quantum.Arrays.ForEach
title: Förställnings åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730238"
---
# <a name="foreach-operation"></a><span data-ttu-id="afaa0-102">Förställnings åtgärd</span><span class="sxs-lookup"><span data-stu-id="afaa0-102">ForEach operation</span></span>

<span data-ttu-id="afaa0-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afaa0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afaa0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afaa0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afaa0-105">Med en matris och en åtgärd som har definierats för elementen i matrisen returnerar en ny matris som består av de avbildningar av den ursprungliga matrisen under åtgärden.</span><span class="sxs-lookup"><span data-stu-id="afaa0-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="afaa0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="afaa0-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="afaa0-107">åtgärd: s => ' U</span><span class="sxs-lookup"><span data-stu-id="afaa0-107">action : 'T => 'U</span></span> 

<span data-ttu-id="afaa0-108">En åtgärd från `'T` till `'U` som tillämpas på varje-element.</span><span class="sxs-lookup"><span data-stu-id="afaa0-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="afaa0-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="afaa0-109">array : 'T[]</span></span>

<span data-ttu-id="afaa0-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="afaa0-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="afaa0-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="afaa0-111">Output : 'U[]</span></span>

<span data-ttu-id="afaa0-112">En matris `'U[]` med element som mappas av `action` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="afaa0-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afaa0-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="afaa0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afaa0-114">Inte</span><span class="sxs-lookup"><span data-stu-id="afaa0-114">'T</span></span>

<span data-ttu-id="afaa0-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="afaa0-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="afaa0-116">' U</span><span class="sxs-lookup"><span data-stu-id="afaa0-116">'U</span></span>

<span data-ttu-id="afaa0-117">`action`Åtgärdens resultat typ.</span><span class="sxs-lookup"><span data-stu-id="afaa0-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="afaa0-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="afaa0-118">Remarks</span></span>

<span data-ttu-id="afaa0-119">Åtgärden definieras för generiska typer, dvs. När vi har en matris `'T[]` och en åtgärd `action : 'T -> 'U` kan vi mappa element i matrisen och skapa en ny matris av typen `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="afaa0-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>