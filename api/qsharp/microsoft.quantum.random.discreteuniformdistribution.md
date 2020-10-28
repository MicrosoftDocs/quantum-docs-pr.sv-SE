---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Funktionen DiscreteUniformDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730966"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="c3404-102">Funktionen DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="c3404-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="c3404-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c3404-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c3404-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3404-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3404-105">Returnerar en enhetlig distribution över ett angivet inklusivt intervall.</span><span class="sxs-lookup"><span data-stu-id="c3404-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="c3404-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c3404-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="c3404-107">min: [heltal](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3404-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3404-108">Det minsta heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="c3404-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="c3404-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3404-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3404-110">Det största heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="c3404-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="c3404-111">Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c3404-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c3404-112">En distribution vars slumpmässiga variates är heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="c3404-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3404-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c3404-113">Remarks</span></span>

<span data-ttu-id="c3404-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c3404-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3404-115">Se även</span><span class="sxs-lookup"><span data-stu-id="c3404-115">See Also</span></span>

- [<span data-ttu-id="c3404-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c3404-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)