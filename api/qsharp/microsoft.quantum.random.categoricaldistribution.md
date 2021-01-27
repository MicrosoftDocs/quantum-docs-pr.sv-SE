---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Funktionen CategoricalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842349"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="7ea49-102">Funktionen CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="7ea49-102">CategoricalDistribution function</span></span>

<span data-ttu-id="7ea49-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="7ea49-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="7ea49-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7ea49-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7ea49-105">Returnerar en diskret kategoriska-distribution där sannolikheten för var och en av de givna resultat som anges uttryckligen anges.</span><span class="sxs-lookup"><span data-stu-id="7ea49-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="7ea49-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7ea49-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="7ea49-107">sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7ea49-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7ea49-108">Sannolikheten för varje resultat från kategoriska-distributionen.</span><span class="sxs-lookup"><span data-stu-id="7ea49-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="7ea49-109">Dessa sannolikheter kanske inte är normaliserade men måste vara icke-negativa.</span><span class="sxs-lookup"><span data-stu-id="7ea49-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="7ea49-110">Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="7ea49-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="7ea49-111">Indexet `i` med sannolikhet `probs[i] / sum` , där `sum` är summan av `probs` `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="7ea49-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="7ea49-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="7ea49-112">Example</span></span>

<span data-ttu-id="7ea49-113">Följande Q #-kod visar 0 med sannolikhet 30% och 1 med sannolikhet 70%:</span><span class="sxs-lookup"><span data-stu-id="7ea49-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```