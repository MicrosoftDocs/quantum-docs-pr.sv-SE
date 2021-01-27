---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Funktionen DiscreteUniformDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853725"
---
# <a name="discreteuniformdistribution-function"></a>Funktionen DiscreteUniformDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar en enhetlig distribution över ett angivet inklusivt intervall.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Indata

### <a name="min--int"></a>min: [heltal](xref:microsoft.quantum.lang-ref.int)

Det minsta heltal som ska ritas.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Det största heltal som ska ritas.



## <a name="output--discretedistribution"></a>Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

En distribution vars slumpmässiga variates är heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.

## <a name="example"></a>Exempel

Följande Q #-kodfragment rullar slumpmässigt en sida med sex sidor:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)