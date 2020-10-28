---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Funktionen RectangularArrayFact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730051"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="8e1fb-102">Funktionen RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="8e1fb-102">RectangularArrayFact function</span></span>

<span data-ttu-id="8e1fb-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8e1fb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8e1fb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e1fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e1fb-105">Representerar ett villkor som en tvådimensionell matris har en rektangulär figur</span><span class="sxs-lookup"><span data-stu-id="8e1fb-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="8e1fb-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8e1fb-106">Description</span></span>

<span data-ttu-id="8e1fb-107">Den här funktionen förutsätter att varje rad i en matris har samma längd.</span><span class="sxs-lookup"><span data-stu-id="8e1fb-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="8e1fb-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8e1fb-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="8e1fb-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="8e1fb-109">array : 'T[][]</span></span>

<span data-ttu-id="8e1fb-110">En tvådimensionell matris med element</span><span class="sxs-lookup"><span data-stu-id="8e1fb-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="8e1fb-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8e1fb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8e1fb-112">Ett meddelande som skrivs ut om matrisen inte är en rektangulär matris</span><span class="sxs-lookup"><span data-stu-id="8e1fb-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e1fb-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e1fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8e1fb-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8e1fb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e1fb-115">Inte</span><span class="sxs-lookup"><span data-stu-id="8e1fb-115">'T</span></span>

<span data-ttu-id="8e1fb-116">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="8e1fb-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e1fb-117">Se även</span><span class="sxs-lookup"><span data-stu-id="8e1fb-117">See Also</span></span>

- [<span data-ttu-id="8e1fb-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="8e1fb-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)