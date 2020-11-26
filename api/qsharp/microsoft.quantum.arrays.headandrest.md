---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Funktionen HeadAndRest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221087"
---
# <a name="headandrest-function"></a><span data-ttu-id="fe521-102">Funktionen HeadAndRest</span><span class="sxs-lookup"><span data-stu-id="fe521-102">HeadAndRest function</span></span>

<span data-ttu-id="fe521-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe521-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe521-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe521-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe521-105">Returnerar en tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="fe521-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="fe521-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fe521-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fe521-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="fe521-107">array : 'A[]</span></span>

<span data-ttu-id="fe521-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="fe521-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="fe521-109">Utdata: ("A" A [])</span><span class="sxs-lookup"><span data-stu-id="fe521-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="fe521-110">En tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="fe521-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe521-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fe521-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fe521-112">"A</span><span class="sxs-lookup"><span data-stu-id="fe521-112">'A</span></span>

<span data-ttu-id="fe521-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="fe521-113">The type of the array elements.</span></span>