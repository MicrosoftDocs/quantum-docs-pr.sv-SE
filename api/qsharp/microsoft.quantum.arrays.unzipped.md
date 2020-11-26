---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Unzippad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219965"
---
# <a name="unzipped-function"></a><span data-ttu-id="d9892-102">Unzippad funktion</span><span class="sxs-lookup"><span data-stu-id="d9892-102">Unzipped function</span></span>

<span data-ttu-id="d9892-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d9892-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d9892-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9892-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9892-105">Med en matris med 2-tupler returnerar en tupel av två matriser, där varje innehåller elementen i tuppeln för den inmatade matrisen.</span><span class="sxs-lookup"><span data-stu-id="d9892-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="d9892-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d9892-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="d9892-107">arr: (t. ex. ' U) []</span><span class="sxs-lookup"><span data-stu-id="d9892-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="d9892-108">En matris som innehåller 2-tupler</span><span class="sxs-lookup"><span data-stu-id="d9892-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="d9892-109">Utdata: (inte [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="d9892-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="d9892-110">Två matriser, det första som innehåller alla första element i indatavärdena, den andra som innehåller alla andra element i indatavärdena.</span><span class="sxs-lookup"><span data-stu-id="d9892-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9892-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d9892-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9892-112">Inte</span><span class="sxs-lookup"><span data-stu-id="d9892-112">'T</span></span>

<span data-ttu-id="d9892-113">Typen för det första elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="d9892-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="d9892-114">' U</span><span class="sxs-lookup"><span data-stu-id="d9892-114">'U</span></span>

<span data-ttu-id="d9892-115">Typen för det andra elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="d9892-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="d9892-116">Se även</span><span class="sxs-lookup"><span data-stu-id="d9892-116">See Also</span></span>

- [<span data-ttu-id="d9892-117">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="d9892-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)