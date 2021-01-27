---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Unzippad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845368"
---
# <a name="unzipped-function"></a><span data-ttu-id="d07bf-102">Unzippad funktion</span><span class="sxs-lookup"><span data-stu-id="d07bf-102">Unzipped function</span></span>

<span data-ttu-id="d07bf-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d07bf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d07bf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d07bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d07bf-105">Med en matris med 2-tupler returnerar en tupel av två matriser, där varje innehåller elementen i tuppeln för den inmatade matrisen.</span><span class="sxs-lookup"><span data-stu-id="d07bf-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="d07bf-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d07bf-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="d07bf-107">arr: (t. ex. ' U) []</span><span class="sxs-lookup"><span data-stu-id="d07bf-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="d07bf-108">En matris som innehåller 2-tupler</span><span class="sxs-lookup"><span data-stu-id="d07bf-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="d07bf-109">Utdata: (inte [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="d07bf-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="d07bf-110">Två matriser, det första som innehåller alla första element i indatavärdena, den andra som innehåller alla andra element i indatavärdena.</span><span class="sxs-lookup"><span data-stu-id="d07bf-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d07bf-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d07bf-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d07bf-112">Inte</span><span class="sxs-lookup"><span data-stu-id="d07bf-112">'T</span></span>

<span data-ttu-id="d07bf-113">Typen för det första elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="d07bf-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="d07bf-114">' U</span><span class="sxs-lookup"><span data-stu-id="d07bf-114">'U</span></span>

<span data-ttu-id="d07bf-115">Typen för det andra elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="d07bf-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="d07bf-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="d07bf-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="d07bf-117">Se även</span><span class="sxs-lookup"><span data-stu-id="d07bf-117">See Also</span></span>

- [<span data-ttu-id="d07bf-118">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="d07bf-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)