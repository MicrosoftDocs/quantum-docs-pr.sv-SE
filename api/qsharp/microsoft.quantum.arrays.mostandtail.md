---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Funktionen MostAndTail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220577"
---
# <a name="mostandtail-function"></a><span data-ttu-id="b67fe-102">Funktionen MostAndTail</span><span class="sxs-lookup"><span data-stu-id="b67fe-102">MostAndTail function</span></span>

<span data-ttu-id="b67fe-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b67fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b67fe-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b67fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b67fe-105">Returnerar en tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="b67fe-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="b67fe-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b67fe-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="b67fe-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="b67fe-107">array : 'A[]</span></span>

<span data-ttu-id="b67fe-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="b67fe-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="b67fe-109">Utdata: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="b67fe-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="b67fe-110">En tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="b67fe-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b67fe-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b67fe-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="b67fe-112">"A</span><span class="sxs-lookup"><span data-stu-id="b67fe-112">'A</span></span>

<span data-ttu-id="b67fe-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="b67fe-113">The type of the array elements.</span></span>