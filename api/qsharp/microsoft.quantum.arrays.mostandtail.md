---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Funktionen MostAndTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845590"
---
# <a name="mostandtail-function"></a><span data-ttu-id="54ce2-102">Funktionen MostAndTail</span><span class="sxs-lookup"><span data-stu-id="54ce2-102">MostAndTail function</span></span>

<span data-ttu-id="54ce2-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="54ce2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="54ce2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54ce2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54ce2-105">Returnerar en tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="54ce2-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="54ce2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="54ce2-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="54ce2-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="54ce2-107">array : 'A[]</span></span>

<span data-ttu-id="54ce2-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="54ce2-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="54ce2-109">Utdata: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="54ce2-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="54ce2-110">En tupel av alla utom ett och det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="54ce2-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="54ce2-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="54ce2-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="54ce2-112">"A</span><span class="sxs-lookup"><span data-stu-id="54ce2-112">'A</span></span>

<span data-ttu-id="54ce2-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="54ce2-113">The type of the array elements.</span></span>