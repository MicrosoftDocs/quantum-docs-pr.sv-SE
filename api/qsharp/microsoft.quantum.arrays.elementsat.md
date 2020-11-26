---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: Funktionen ElementsAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221461"
---
# <a name="elementsat-function"></a><span data-ttu-id="784c4-102">Funktionen ElementsAt</span><span class="sxs-lookup"><span data-stu-id="784c4-102">ElementsAt function</span></span>

<span data-ttu-id="784c4-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="784c4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="784c4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="784c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="784c4-105">Returnerar matrisens element i ett angivet intervall av index.</span><span class="sxs-lookup"><span data-stu-id="784c4-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="784c4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="784c4-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="784c4-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="784c4-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="784c4-108">Intervall med mat ris index</span><span class="sxs-lookup"><span data-stu-id="784c4-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="784c4-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="784c4-109">array : 'T[]</span></span>

<span data-ttu-id="784c4-110">Matris</span><span class="sxs-lookup"><span data-stu-id="784c4-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="784c4-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="784c4-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="784c4-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="784c4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="784c4-113">Inte</span><span class="sxs-lookup"><span data-stu-id="784c4-113">'T</span></span>

<span data-ttu-id="784c4-114">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="784c4-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="784c4-115">Se även</span><span class="sxs-lookup"><span data-stu-id="784c4-115">See Also</span></span>

- [<span data-ttu-id="784c4-116">Microsoft. Quantum. Arrays. ElementAt</span><span class="sxs-lookup"><span data-stu-id="784c4-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="784c4-117">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="784c4-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)