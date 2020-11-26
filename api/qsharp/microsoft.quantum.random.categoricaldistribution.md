---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Funktionen CategoricalDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210258"
---
# <a name="categoricaldistribution-function"></a>Funktionen CategoricalDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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