---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Funktionen TransformedContinuousDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226272"
---
# <a name="transformedcontinuousdistribution-function"></a>Funktionen TransformedContinuousDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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