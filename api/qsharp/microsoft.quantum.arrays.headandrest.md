---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Funktionen HeadAndRest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730222"
---
# <a name="headandrest-function"></a><span data-ttu-id="146cf-102">Funktionen HeadAndRest</span><span class="sxs-lookup"><span data-stu-id="146cf-102">HeadAndRest function</span></span>

<span data-ttu-id="146cf-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="146cf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="146cf-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="146cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="146cf-105">Returnerar en tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="146cf-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="146cf-106">Indata</span><span class="sxs-lookup"><span data-stu-id="146cf-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="146cf-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="146cf-107">array : 'A[]</span></span>

<span data-ttu-id="146cf-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="146cf-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="146cf-109">Utdata: ("A" A [])</span><span class="sxs-lookup"><span data-stu-id="146cf-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="146cf-110">En tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="146cf-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="146cf-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="146cf-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="146cf-112">"A</span><span class="sxs-lookup"><span data-stu-id="146cf-112">'A</span></span>

<span data-ttu-id="146cf-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="146cf-113">The type of the array elements.</span></span>