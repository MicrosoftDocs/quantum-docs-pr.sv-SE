---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Funktionen SquareArrayFact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730006"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="72a46-102">Funktionen SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="72a46-102">SquareArrayFact function</span></span>

<span data-ttu-id="72a46-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="72a46-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="72a46-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72a46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72a46-105">Representerar ett villkor som en tvådimensionell matris har en kvadratisk form</span><span class="sxs-lookup"><span data-stu-id="72a46-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="72a46-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="72a46-106">Description</span></span>

<span data-ttu-id="72a46-107">Den här funktionen förutsätter att varje rad i en matris har så många element som det finns rader (element) i matrisen.</span><span class="sxs-lookup"><span data-stu-id="72a46-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="72a46-108">Indata</span><span class="sxs-lookup"><span data-stu-id="72a46-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="72a46-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="72a46-109">array : 'T[][]</span></span>

<span data-ttu-id="72a46-110">En tvådimensionell matris med element</span><span class="sxs-lookup"><span data-stu-id="72a46-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="72a46-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="72a46-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="72a46-112">Ett meddelande som skrivs ut om matrisen inte är en hak mat ris</span><span class="sxs-lookup"><span data-stu-id="72a46-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="72a46-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72a46-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72a46-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="72a46-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72a46-115">Inte</span><span class="sxs-lookup"><span data-stu-id="72a46-115">'T</span></span>

<span data-ttu-id="72a46-116">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="72a46-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="72a46-117">Se även</span><span class="sxs-lookup"><span data-stu-id="72a46-117">See Also</span></span>

- [<span data-ttu-id="72a46-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="72a46-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)