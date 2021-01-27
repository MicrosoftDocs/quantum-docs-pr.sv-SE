---
uid: Microsoft.Quantum.Arrays.ElementAt
title: Funktionen ElementAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842808"
---
# <a name="elementat-function"></a><span data-ttu-id="3b39e-102">Funktionen ElementAt</span><span class="sxs-lookup"><span data-stu-id="3b39e-102">ElementAt function</span></span>

<span data-ttu-id="3b39e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3b39e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3b39e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b39e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b39e-105">Returnerar vid det aktuella indexet för en matris.</span><span class="sxs-lookup"><span data-stu-id="3b39e-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="3b39e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3b39e-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="3b39e-107">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b39e-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b39e-108">Index för element</span><span class="sxs-lookup"><span data-stu-id="3b39e-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="3b39e-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="3b39e-109">array : 'T[]</span></span>

<span data-ttu-id="3b39e-110">Matrisen som indexeras.</span><span class="sxs-lookup"><span data-stu-id="3b39e-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="3b39e-111">Utdata: ' t</span><span class="sxs-lookup"><span data-stu-id="3b39e-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3b39e-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3b39e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b39e-113">Inte</span><span class="sxs-lookup"><span data-stu-id="3b39e-113">'T</span></span>

<span data-ttu-id="3b39e-114">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="3b39e-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="3b39e-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="3b39e-115">Example</span></span>

<span data-ttu-id="3b39e-116">Hämta det tredje talet i fyra berömda heltals sekvenser.</span><span class="sxs-lookup"><span data-stu-id="3b39e-116">Get the third number in four famous integer sequences.</span></span> <span data-ttu-id="3b39e-117">(Observera att indexet 0 motsvarar det _första_ värdet i sekvensen.)</span><span class="sxs-lookup"><span data-stu-id="3b39e-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a><span data-ttu-id="3b39e-118">Se även</span><span class="sxs-lookup"><span data-stu-id="3b39e-118">See Also</span></span>

- [<span data-ttu-id="3b39e-119">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="3b39e-119">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="3b39e-120">Microsoft. Quantum. Arrays. ElementsAt</span><span class="sxs-lookup"><span data-stu-id="3b39e-120">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)