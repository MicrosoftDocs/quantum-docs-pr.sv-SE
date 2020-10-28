---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Funktionen TransformedContinuousDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726460"
---
# <a name="transformedcontinuousdistribution-function"></a>Funktionen TransformedContinuousDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Med en kontinuerlig distribution returnerar en ny distribution som transformerar originalet med en specifik funktion.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Indata

### <a name="transform--double---double"></a>transformering: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)

En funktion som transformerar variates för den ursprungliga distributionen till den transformerade distributionen.


### <a name="distribution--continuousdistribution"></a>distribution: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Den ursprungliga fördelningen som ska omvandlas.



## <a name="output--continuousdistribution"></a>Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

En ny distribution som är relaterad till `distribution` av transformeringen som erhålls av `transform` .