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
# <a name="categoricaldistribution-function"></a>Funktionen CategoricalDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Returnerar en diskret kategoriska-distribution där sannolikheten för var och en av de givna resultat som anges uttryckligen anges.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Indata

### <a name="probs--double"></a>sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Sannolikheten för varje resultat från kategoriska-distributionen.
Dessa sannolikheter kanske inte är normaliserade men måste vara icke-negativa.



## <a name="output--discretedistribution"></a>Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Indexet `i` med sannolikhet `probs[i] / sum` , där `sum` är summan av `probs` `Fold(PlusD, 0.0, probs)` .