---
uid: Microsoft.Quantum.Arrays.ForEach
title: Förställnings åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848588"
---
# <a name="foreach-operation"></a><span data-ttu-id="9847e-102">Förställnings åtgärd</span><span class="sxs-lookup"><span data-stu-id="9847e-102">ForEach operation</span></span>

<span data-ttu-id="9847e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9847e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9847e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9847e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9847e-105">Med en matris och en åtgärd som har definierats för elementen i matrisen returnerar en ny matris som består av de avbildningar av den ursprungliga matrisen under åtgärden.</span><span class="sxs-lookup"><span data-stu-id="9847e-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="9847e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9847e-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="9847e-107">åtgärd: s => ' U</span><span class="sxs-lookup"><span data-stu-id="9847e-107">action : 'T => 'U</span></span> 

<span data-ttu-id="9847e-108">En åtgärd från `'T` till `'U` som tillämpas på varje-element.</span><span class="sxs-lookup"><span data-stu-id="9847e-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="9847e-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="9847e-109">array : 'T[]</span></span>

<span data-ttu-id="9847e-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="9847e-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="9847e-111">Utdata: U []</span><span class="sxs-lookup"><span data-stu-id="9847e-111">Output : 'U[]</span></span>

<span data-ttu-id="9847e-112">En matris `'U[]` med element som mappas av `action` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="9847e-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9847e-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9847e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9847e-114">Inte</span><span class="sxs-lookup"><span data-stu-id="9847e-114">'T</span></span>

<span data-ttu-id="9847e-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="9847e-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="9847e-116">' U</span><span class="sxs-lookup"><span data-stu-id="9847e-116">'U</span></span>

<span data-ttu-id="9847e-117">`action`Åtgärdens resultat typ.</span><span class="sxs-lookup"><span data-stu-id="9847e-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="9847e-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9847e-118">Remarks</span></span>

<span data-ttu-id="9847e-119">Åtgärden definieras för generiska typer, dvs. När vi har en matris `'T[]` och en åtgärd `action : 'T -> 'U` kan vi mappa element i matrisen och skapa en ny matris av typen `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="9847e-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>