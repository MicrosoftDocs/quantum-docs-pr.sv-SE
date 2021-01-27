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

## <a name="example"></a>Exempel

Följande Q #-kod visar 0 med sannolikhet 30% och 1 med sannolikhet 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```