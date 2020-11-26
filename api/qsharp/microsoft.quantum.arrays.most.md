---
uid: Microsoft.Quantum.Arrays.Most
title: De flesta funktioner
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220611"
---
# <a name="most-function"></a><span data-ttu-id="23503-102">De flesta funktioner</span><span class="sxs-lookup"><span data-stu-id="23503-102">Most function</span></span>

<span data-ttu-id="23503-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23503-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23503-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23503-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23503-105">Skapar en matris som är lika med en indataparameter förutom att det sista mat ris elementet har släppts.</span><span class="sxs-lookup"><span data-stu-id="23503-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="23503-106">Indata</span><span class="sxs-lookup"><span data-stu-id="23503-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="23503-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="23503-107">array : 'T[]</span></span>

<span data-ttu-id="23503-108">En matris vars första till-sista-element är att skapa en matris för utdata.</span><span class="sxs-lookup"><span data-stu-id="23503-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="23503-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="23503-109">Output : 'T[]</span></span>

<span data-ttu-id="23503-110">En matris som innehåller elementen `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="23503-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23503-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="23503-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23503-112">Inte</span><span class="sxs-lookup"><span data-stu-id="23503-112">'T</span></span>

<span data-ttu-id="23503-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="23503-113">The type of the array elements.</span></span>