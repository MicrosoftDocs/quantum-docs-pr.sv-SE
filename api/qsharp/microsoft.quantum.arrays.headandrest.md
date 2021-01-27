---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Funktionen HeadAndRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848547"
---
# <a name="headandrest-function"></a><span data-ttu-id="04097-102">Funktionen HeadAndRest</span><span class="sxs-lookup"><span data-stu-id="04097-102">HeadAndRest function</span></span>

<span data-ttu-id="04097-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="04097-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="04097-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04097-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04097-105">Returnerar en tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="04097-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="04097-106">Indata</span><span class="sxs-lookup"><span data-stu-id="04097-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="04097-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="04097-107">array : 'A[]</span></span>

<span data-ttu-id="04097-108">En matris med minst ett element.</span><span class="sxs-lookup"><span data-stu-id="04097-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="04097-109">Utdata: ("A" A [])</span><span class="sxs-lookup"><span data-stu-id="04097-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="04097-110">En tupel av de första och alla återstående element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="04097-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="04097-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="04097-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="04097-112">"A</span><span class="sxs-lookup"><span data-stu-id="04097-112">'A</span></span>

<span data-ttu-id="04097-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="04097-113">The type of the array elements.</span></span>