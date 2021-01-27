---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Funktionen IndexRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845784"
---
# <a name="indexrange-function"></a><span data-ttu-id="58b23-102">Funktionen IndexRange</span><span class="sxs-lookup"><span data-stu-id="58b23-102">IndexRange function</span></span>

<span data-ttu-id="58b23-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="58b23-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="58b23-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="58b23-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="58b23-105">Med den här matrisen returneras ett intervall över indexets index, vilket är lämpligt för användning i en for-slinga.</span><span class="sxs-lookup"><span data-stu-id="58b23-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="58b23-106">Indata</span><span class="sxs-lookup"><span data-stu-id="58b23-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="58b23-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="58b23-107">array : 'TElement[]</span></span>

<span data-ttu-id="58b23-108">En matris som en serie index ska returneras för.</span><span class="sxs-lookup"><span data-stu-id="58b23-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="58b23-109">Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="58b23-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="58b23-110">Ett intervall över alla index i matrisen.</span><span class="sxs-lookup"><span data-stu-id="58b23-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58b23-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="58b23-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="58b23-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="58b23-112">'TElement</span></span>

<span data-ttu-id="58b23-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="58b23-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="58b23-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="58b23-114">Example</span></span>

<span data-ttu-id="58b23-115">Följande `for` slingor är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="58b23-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```