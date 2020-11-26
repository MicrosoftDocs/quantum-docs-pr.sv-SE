---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Funktionen RectangularArrayFact
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220424"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="bc840-102">Funktionen RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="bc840-102">RectangularArrayFact function</span></span>

<span data-ttu-id="bc840-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc840-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc840-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc840-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc840-105">Representerar ett villkor som en tvådimensionell matris har en rektangulär figur</span><span class="sxs-lookup"><span data-stu-id="bc840-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="bc840-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bc840-106">Description</span></span>

<span data-ttu-id="bc840-107">Den här funktionen förutsätter att varje rad i en matris har samma längd.</span><span class="sxs-lookup"><span data-stu-id="bc840-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="bc840-108">Indata</span><span class="sxs-lookup"><span data-stu-id="bc840-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bc840-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="bc840-109">array : 'T[][]</span></span>

<span data-ttu-id="bc840-110">En tvådimensionell matris med element</span><span class="sxs-lookup"><span data-stu-id="bc840-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="bc840-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bc840-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bc840-112">Ett meddelande som skrivs ut om matrisen inte är en rektangulär matris</span><span class="sxs-lookup"><span data-stu-id="bc840-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc840-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc840-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc840-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bc840-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc840-115">Inte</span><span class="sxs-lookup"><span data-stu-id="bc840-115">'T</span></span>

<span data-ttu-id="bc840-116">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="bc840-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc840-117">Se även</span><span class="sxs-lookup"><span data-stu-id="bc840-117">See Also</span></span>

- [<span data-ttu-id="bc840-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="bc840-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)