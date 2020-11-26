---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Funktionen ContinuousUniformDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193088"
---
# <a name="continuousuniformdistribution-function"></a>Funktionen ContinuousUniformDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar en enhetlig distribution över ett angivet inklusiv-intervall.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Indata

### <a name="min--double"></a>min: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det minsta reella tal som ska ritas.


### <a name="max--double"></a>Max: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det största reella tal som ska ritas.



## <a name="output--continuousdistribution"></a>Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

En distribution vars slumpmässiga variates är reella tal i inklusiv-intervallet från `min` till `max` med enhetlig sannolikhet.

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)