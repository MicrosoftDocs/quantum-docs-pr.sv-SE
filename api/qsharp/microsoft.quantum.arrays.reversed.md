---
uid: Microsoft.Quantum.Arrays.Reversed
title: Omvänd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845460"
---
# <a name="reversed-function"></a><span data-ttu-id="a2f15-102">Omvänd funktion</span><span class="sxs-lookup"><span data-stu-id="a2f15-102">Reversed function</span></span>

<span data-ttu-id="a2f15-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a2f15-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a2f15-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2f15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2f15-105">Skapa en matris som innehåller samma element som en inmatad matris men i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="a2f15-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a2f15-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a2f15-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a2f15-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="a2f15-107">array : 'T[]</span></span>

<span data-ttu-id="a2f15-108">En matris vars element ska kopieras i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="a2f15-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="a2f15-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="a2f15-109">Output : 'T[]</span></span>

<span data-ttu-id="a2f15-110">En matris som innehåller elementen `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="a2f15-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="a2f15-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="a2f15-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a2f15-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a2f15-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2f15-113">Inte</span><span class="sxs-lookup"><span data-stu-id="a2f15-113">'T</span></span>

<span data-ttu-id="a2f15-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="a2f15-114">The type of the array elements.</span></span>