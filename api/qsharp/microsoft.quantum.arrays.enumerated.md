---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Uppräknad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221427"
---
# <a name="enumerated-function"></a><span data-ttu-id="7e0bc-102">Uppräknad funktion</span><span class="sxs-lookup"><span data-stu-id="7e0bc-102">Enumerated function</span></span>

<span data-ttu-id="7e0bc-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7e0bc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7e0bc-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e0bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e0bc-105">Med en matris returneras en ny matris som innehåller element från den ursprungliga matrisen tillsammans med indexen för varje element.</span><span class="sxs-lookup"><span data-stu-id="7e0bc-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="7e0bc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7e0bc-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="7e0bc-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="7e0bc-107">array : 'TElement[]</span></span>

<span data-ttu-id="7e0bc-108">En matris vars element ska räknas upp.</span><span class="sxs-lookup"><span data-stu-id="7e0bc-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="7e0bc-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), "teleteleering) []</span><span class="sxs-lookup"><span data-stu-id="7e0bc-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="7e0bc-110">En ny matris som innehåller element i den ursprungliga matrisen tillsammans med deras index.</span><span class="sxs-lookup"><span data-stu-id="7e0bc-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7e0bc-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7e0bc-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="7e0bc-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="7e0bc-112">'TElement</span></span>

<span data-ttu-id="7e0bc-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="7e0bc-113">The type of elements of the array.</span></span>