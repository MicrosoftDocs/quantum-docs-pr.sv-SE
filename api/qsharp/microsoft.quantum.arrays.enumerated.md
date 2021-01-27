---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Uppräknad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848130"
---
# <a name="enumerated-function"></a><span data-ttu-id="219dd-102">Uppräknad funktion</span><span class="sxs-lookup"><span data-stu-id="219dd-102">Enumerated function</span></span>

<span data-ttu-id="219dd-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="219dd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="219dd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="219dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="219dd-105">Med en matris returneras en ny matris som innehåller element från den ursprungliga matrisen tillsammans med indexen för varje element.</span><span class="sxs-lookup"><span data-stu-id="219dd-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="219dd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="219dd-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="219dd-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="219dd-107">array : 'TElement[]</span></span>

<span data-ttu-id="219dd-108">En matris vars element ska räknas upp.</span><span class="sxs-lookup"><span data-stu-id="219dd-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="219dd-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), "teleteleering) []</span><span class="sxs-lookup"><span data-stu-id="219dd-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="219dd-110">En ny matris som innehåller element i den ursprungliga matrisen tillsammans med deras index.</span><span class="sxs-lookup"><span data-stu-id="219dd-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="219dd-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="219dd-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="219dd-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="219dd-112">'TElement</span></span>

<span data-ttu-id="219dd-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="219dd-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="219dd-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="219dd-114">Example</span></span>

<span data-ttu-id="219dd-115">Följande `for` slingor är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="219dd-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```