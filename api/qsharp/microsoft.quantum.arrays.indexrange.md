---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Funktionen IndexRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730203"
---
# <a name="indexrange-function"></a><span data-ttu-id="ecf78-102">Funktionen IndexRange</span><span class="sxs-lookup"><span data-stu-id="ecf78-102">IndexRange function</span></span>

<span data-ttu-id="ecf78-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ecf78-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ecf78-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecf78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecf78-105">Med den här matrisen returneras ett intervall över indexets index, vilket är lämpligt för användning i en for-slinga.</span><span class="sxs-lookup"><span data-stu-id="ecf78-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="ecf78-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ecf78-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="ecf78-107">matris: ' TEleation []</span><span class="sxs-lookup"><span data-stu-id="ecf78-107">array : 'TElement[]</span></span>

<span data-ttu-id="ecf78-108">En matris som en serie index ska returneras för.</span><span class="sxs-lookup"><span data-stu-id="ecf78-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="ecf78-109">Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ecf78-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ecf78-110">Ett intervall över alla index i matrisen.</span><span class="sxs-lookup"><span data-stu-id="ecf78-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ecf78-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ecf78-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="ecf78-112">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="ecf78-112">'TElement</span></span>

<span data-ttu-id="ecf78-113">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="ecf78-113">The type of elements of the array.</span></span>