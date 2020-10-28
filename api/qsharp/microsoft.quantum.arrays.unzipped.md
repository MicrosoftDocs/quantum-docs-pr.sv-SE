---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Unzippad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729963"
---
# <a name="unzipped-function"></a><span data-ttu-id="054bb-102">Unzippad funktion</span><span class="sxs-lookup"><span data-stu-id="054bb-102">Unzipped function</span></span>

<span data-ttu-id="054bb-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="054bb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="054bb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="054bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="054bb-105">Med en matris med 2-tupler returnerar en tupel av två matriser, där varje innehåller elementen i tuppeln för den inmatade matrisen.</span><span class="sxs-lookup"><span data-stu-id="054bb-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="054bb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="054bb-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="054bb-107">arr: (t. ex. ' U) []</span><span class="sxs-lookup"><span data-stu-id="054bb-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="054bb-108">En matris som innehåller 2-tupler</span><span class="sxs-lookup"><span data-stu-id="054bb-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="054bb-109">Utdata: (inte [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="054bb-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="054bb-110">Två matriser, det första som innehåller alla första element i indatavärdena, den andra som innehåller alla andra element i indatavärdena.</span><span class="sxs-lookup"><span data-stu-id="054bb-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="054bb-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="054bb-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="054bb-112">Inte</span><span class="sxs-lookup"><span data-stu-id="054bb-112">'T</span></span>

<span data-ttu-id="054bb-113">Typen för det första elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="054bb-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="054bb-114">' U</span><span class="sxs-lookup"><span data-stu-id="054bb-114">'U</span></span>

<span data-ttu-id="054bb-115">Typen för det andra elementet i varje tupel</span><span class="sxs-lookup"><span data-stu-id="054bb-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="054bb-116">Se även</span><span class="sxs-lookup"><span data-stu-id="054bb-116">See Also</span></span>

- [<span data-ttu-id="054bb-117">Microsoft.Quantum.Arrays.Zipinmatningsenhet</span><span class="sxs-lookup"><span data-stu-id="054bb-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)