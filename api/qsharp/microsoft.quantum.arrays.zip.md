---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850902"
---
# <a name="zip-function"></a><span data-ttu-id="f01e7-102">Zip-funktion</span><span class="sxs-lookup"><span data-stu-id="f01e7-102">Zip function</span></span>

<span data-ttu-id="f01e7-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f01e7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f01e7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f01e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f01e7-105">Zip är inaktuellt.</span><span class="sxs-lookup"><span data-stu-id="f01e7-105">Zip has been deprecated.</span></span> <span data-ttu-id="f01e7-106">Använd <xref:Microsoft.Quantum.Arrays.Zipped> i stället.</span><span class="sxs-lookup"><span data-stu-id="f01e7-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="f01e7-107">Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.</span><span class="sxs-lookup"><span data-stu-id="f01e7-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="f01e7-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f01e7-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="f01e7-109">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="f01e7-109">left : 'T[]</span></span>

<span data-ttu-id="f01e7-110">En matris som innehåller värden för det första elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="f01e7-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="f01e7-111">höger: U []</span><span class="sxs-lookup"><span data-stu-id="f01e7-111">right : 'U[]</span></span>

<span data-ttu-id="f01e7-112">En matris som innehåller värden för det andra elementet i varje tupel.</span><span class="sxs-lookup"><span data-stu-id="f01e7-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="f01e7-113">Utdata: (t, U) []</span><span class="sxs-lookup"><span data-stu-id="f01e7-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="f01e7-114">En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` .</span><span class="sxs-lookup"><span data-stu-id="f01e7-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="f01e7-115">Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.</span><span class="sxs-lookup"><span data-stu-id="f01e7-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f01e7-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f01e7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f01e7-117">Inte</span><span class="sxs-lookup"><span data-stu-id="f01e7-117">'T</span></span>

<span data-ttu-id="f01e7-118">Typ av vänster mat ris element.</span><span class="sxs-lookup"><span data-stu-id="f01e7-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="f01e7-119">' U</span><span class="sxs-lookup"><span data-stu-id="f01e7-119">'U</span></span>

<span data-ttu-id="f01e7-120">Typ av höger mat ris element.</span><span class="sxs-lookup"><span data-stu-id="f01e7-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="f01e7-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="f01e7-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="f01e7-122">Se även</span><span class="sxs-lookup"><span data-stu-id="f01e7-122">See Also</span></span>

- [<span data-ttu-id="f01e7-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="f01e7-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="f01e7-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="f01e7-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="f01e7-125">Microsoft. Quantum. arrayer. unzippad</span><span class="sxs-lookup"><span data-stu-id="f01e7-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)