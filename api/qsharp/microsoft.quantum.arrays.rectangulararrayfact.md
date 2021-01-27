---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Funktionen RectangularArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845493"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="046fe-102">Funktionen RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="046fe-102">RectangularArrayFact function</span></span>

<span data-ttu-id="046fe-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="046fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="046fe-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="046fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="046fe-105">Representerar ett villkor som en tvådimensionell matris har en rektangulär figur</span><span class="sxs-lookup"><span data-stu-id="046fe-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="046fe-106">Description</span><span class="sxs-lookup"><span data-stu-id="046fe-106">Description</span></span>

<span data-ttu-id="046fe-107">Den här funktionen förutsätter att varje rad i en matris har samma längd.</span><span class="sxs-lookup"><span data-stu-id="046fe-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="046fe-108">Indata</span><span class="sxs-lookup"><span data-stu-id="046fe-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="046fe-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="046fe-109">array : 'T[][]</span></span>

<span data-ttu-id="046fe-110">En tvådimensionell matris med element</span><span class="sxs-lookup"><span data-stu-id="046fe-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="046fe-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="046fe-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="046fe-112">Ett meddelande som skrivs ut om matrisen inte är en rektangulär matris</span><span class="sxs-lookup"><span data-stu-id="046fe-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="046fe-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="046fe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="046fe-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="046fe-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="046fe-115">Inte</span><span class="sxs-lookup"><span data-stu-id="046fe-115">'T</span></span>

<span data-ttu-id="046fe-116">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="046fe-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="046fe-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="046fe-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="046fe-118">Se även</span><span class="sxs-lookup"><span data-stu-id="046fe-118">See Also</span></span>

- [<span data-ttu-id="046fe-119">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="046fe-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)