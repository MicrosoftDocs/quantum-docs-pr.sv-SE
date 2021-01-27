---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Funktionen TransformedContinuousDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857760"
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

## <a name="example"></a>Exempel

Följande två distributioner är identiska:

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```