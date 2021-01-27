---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Funktionen SquareArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850971"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="f9dd2-102">Funktionen SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="f9dd2-102">SquareArrayFact function</span></span>

<span data-ttu-id="f9dd2-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9dd2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9dd2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9dd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9dd2-105">Representerar ett villkor som en tvådimensionell matris har en kvadratisk form</span><span class="sxs-lookup"><span data-stu-id="f9dd2-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="f9dd2-106">Description</span><span class="sxs-lookup"><span data-stu-id="f9dd2-106">Description</span></span>

<span data-ttu-id="f9dd2-107">Den här funktionen förutsätter att varje rad i en matris har så många element som det finns rader (element) i matrisen.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="f9dd2-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f9dd2-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f9dd2-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="f9dd2-109">array : 'T[][]</span></span>

<span data-ttu-id="f9dd2-110">En tvådimensionell matris med element</span><span class="sxs-lookup"><span data-stu-id="f9dd2-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="f9dd2-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f9dd2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f9dd2-112">Ett meddelande som skrivs ut om matrisen inte är en hak mat ris</span><span class="sxs-lookup"><span data-stu-id="f9dd2-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9dd2-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9dd2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9dd2-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f9dd2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9dd2-115">Inte</span><span class="sxs-lookup"><span data-stu-id="f9dd2-115">'T</span></span>

<span data-ttu-id="f9dd2-116">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="f9dd2-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="f9dd2-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="f9dd2-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="f9dd2-118">Se även</span><span class="sxs-lookup"><span data-stu-id="f9dd2-118">See Also</span></span>

- [<span data-ttu-id="f9dd2-119">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="f9dd2-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)