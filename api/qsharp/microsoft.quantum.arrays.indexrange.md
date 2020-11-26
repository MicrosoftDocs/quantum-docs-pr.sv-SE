---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Funktionen IndexRange
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220951"
---
# <a name="indexrange-function"></a><span data-ttu-id="8fb52-102">Funktionen IndexRange</span><span class="sxs-lookup"><span data-stu-id="8fb52-102">IndexRange function</span></span>

<span data-ttu-id="8fb52-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8fb52-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8fb52-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8fb52-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8fb52-105">Med den här matrisen returneras ett intervall över indexets index, vilket är lämpligt för användning i en for-slinga.</span><span class="sxs-lookup"><span data-stu-id="8fb52-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="8fb52-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8fb52-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="8fb52-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="8fb52-107">array : 'TElement[]</span></span>

<span data-ttu-id="8fb52-108">En matris som en serie index ska returneras för.</span><span class="sxs-lookup"><span data-stu-id="8fb52-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="8fb52-109">Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8fb52-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8fb52-110">Ett intervall över alla index i matrisen.</span><span class="sxs-lookup"><span data-stu-id="8fb52-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8fb52-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8fb52-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="8fb52-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="8fb52-112">'TElement</span></span>

<span data-ttu-id="8fb52-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="8fb52-113">The type of elements of the array.</span></span>