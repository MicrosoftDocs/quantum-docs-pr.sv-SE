---
uid: Microsoft.Quantum.Arrays.Reversed
title: Omvänd funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220441"
---
# <a name="reversed-function"></a><span data-ttu-id="c9f33-102">Omvänd funktion</span><span class="sxs-lookup"><span data-stu-id="c9f33-102">Reversed function</span></span>

<span data-ttu-id="c9f33-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c9f33-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c9f33-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9f33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9f33-105">Skapa en matris som innehåller samma element som en inmatad matris men i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="c9f33-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c9f33-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c9f33-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c9f33-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="c9f33-107">array : 'T[]</span></span>

<span data-ttu-id="c9f33-108">En matris vars element ska kopieras i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="c9f33-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="c9f33-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="c9f33-109">Output : 'T[]</span></span>

<span data-ttu-id="c9f33-110">En matris som innehåller elementen `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="c9f33-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="c9f33-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="c9f33-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9f33-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c9f33-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9f33-113">Inte</span><span class="sxs-lookup"><span data-stu-id="c9f33-113">'T</span></span>

<span data-ttu-id="c9f33-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="c9f33-114">The type of the array elements.</span></span>