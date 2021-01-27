---
uid: Microsoft.Quantum.Arrays.Most
title: De flesta funktioner
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845586"
---
# <a name="most-function"></a><span data-ttu-id="2d67a-102">De flesta funktioner</span><span class="sxs-lookup"><span data-stu-id="2d67a-102">Most function</span></span>

<span data-ttu-id="2d67a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2d67a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2d67a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d67a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d67a-105">Skapar en matris som är lika med en indataparameter förutom att det sista mat ris elementet har släppts.</span><span class="sxs-lookup"><span data-stu-id="2d67a-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2d67a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2d67a-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2d67a-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="2d67a-107">array : 'T[]</span></span>

<span data-ttu-id="2d67a-108">En matris vars första till-sista-element är att skapa en matris för utdata.</span><span class="sxs-lookup"><span data-stu-id="2d67a-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2d67a-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="2d67a-109">Output : 'T[]</span></span>

<span data-ttu-id="2d67a-110">En matris som innehåller elementen `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="2d67a-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2d67a-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2d67a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d67a-112">Inte</span><span class="sxs-lookup"><span data-stu-id="2d67a-112">'T</span></span>

<span data-ttu-id="2d67a-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="2d67a-113">The type of the array elements.</span></span>