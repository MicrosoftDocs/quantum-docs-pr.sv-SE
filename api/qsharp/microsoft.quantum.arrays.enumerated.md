---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Uppräknad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730307"
---
# <a name="enumerated-function"></a><span data-ttu-id="559d6-102">Uppräknad funktion</span><span class="sxs-lookup"><span data-stu-id="559d6-102">Enumerated function</span></span>

<span data-ttu-id="559d6-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="559d6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="559d6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="559d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="559d6-105">Med en matris returneras en ny matris som innehåller element från den ursprungliga matrisen tillsammans med indexen för varje element.</span><span class="sxs-lookup"><span data-stu-id="559d6-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="559d6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="559d6-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="559d6-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="559d6-107">array : 'TElement[]</span></span>

<span data-ttu-id="559d6-108">En matris vars element ska räknas upp.</span><span class="sxs-lookup"><span data-stu-id="559d6-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="559d6-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), "teleteleering) []</span><span class="sxs-lookup"><span data-stu-id="559d6-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="559d6-110">En ny matris som innehåller element i den ursprungliga matrisen tillsammans med deras index.</span><span class="sxs-lookup"><span data-stu-id="559d6-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="559d6-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="559d6-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="559d6-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="559d6-112">'TElement</span></span>

<span data-ttu-id="559d6-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="559d6-113">The type of elements of the array.</span></span>