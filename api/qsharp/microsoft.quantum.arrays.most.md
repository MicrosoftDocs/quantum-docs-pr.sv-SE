---
uid: Microsoft.Quantum.Arrays.Most
title: De flesta funktioner
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730102"
---
# <a name="most-function"></a><span data-ttu-id="b1225-102">De flesta funktioner</span><span class="sxs-lookup"><span data-stu-id="b1225-102">Most function</span></span>

<span data-ttu-id="b1225-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b1225-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b1225-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1225-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1225-105">Skapar en matris som är lika med en indataparameter förutom att det sista mat ris elementet har släppts.</span><span class="sxs-lookup"><span data-stu-id="b1225-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b1225-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b1225-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b1225-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="b1225-107">array : 'T[]</span></span>

<span data-ttu-id="b1225-108">En matris vars första till-sista-element är att skapa en matris för utdata.</span><span class="sxs-lookup"><span data-stu-id="b1225-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b1225-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="b1225-109">Output : 'T[]</span></span>

<span data-ttu-id="b1225-110">En matris som innehåller elementen `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="b1225-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b1225-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b1225-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1225-112">Inte</span><span class="sxs-lookup"><span data-stu-id="b1225-112">'T</span></span>

<span data-ttu-id="b1225-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b1225-113">The type of the array elements.</span></span>