---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Funktionen DiscreteUniformDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193020"
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

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)