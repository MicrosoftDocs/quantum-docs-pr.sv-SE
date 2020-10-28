---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Funktionen MostAndTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730099"
---
# <a name="mostandtail-function"></a><span data-ttu-id="80454-102">Funktionen MostAndTail</span><span class="sxs-lookup"><span data-stu-id="80454-102">MostAndTail function</span></span>

<span data-ttu-id="80454-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="80454-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="80454-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80454-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80454-105">Returnerar en tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="80454-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="80454-106">Indata</span><span class="sxs-lookup"><span data-stu-id="80454-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="80454-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="80454-107">array : 'A[]</span></span>

<span data-ttu-id="80454-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="80454-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="80454-109">Utdata: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="80454-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="80454-110">En tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="80454-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80454-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="80454-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="80454-112">"A</span><span class="sxs-lookup"><span data-stu-id="80454-112">'A</span></span>

<span data-ttu-id="80454-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="80454-113">The type of the array elements.</span></span>