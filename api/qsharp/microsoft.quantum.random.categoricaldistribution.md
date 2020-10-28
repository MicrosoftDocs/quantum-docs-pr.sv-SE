---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Funktionen CategoricalDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732542"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="9cf19-102">Funktionen CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="9cf19-102">CategoricalDistribution function</span></span>

<span data-ttu-id="9cf19-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="9cf19-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="9cf19-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cf19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cf19-105">Returnerar en diskret kategoriska-distribution där sannolikheten för var och en av de givna resultat som anges uttryckligen anges.</span><span class="sxs-lookup"><span data-stu-id="9cf19-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="9cf19-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9cf19-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="9cf19-107">sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9cf19-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9cf19-108">Sannolikheten för varje resultat från kategoriska-distributionen.</span><span class="sxs-lookup"><span data-stu-id="9cf19-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="9cf19-109">Dessa sannolikheter kanske inte är normaliserade men måste vara icke-negativa.</span><span class="sxs-lookup"><span data-stu-id="9cf19-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="9cf19-110">Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="9cf19-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="9cf19-111">Indexet `i` med sannolikhet `probs[i] / sum` , där `sum` är summan av `probs` `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="9cf19-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>