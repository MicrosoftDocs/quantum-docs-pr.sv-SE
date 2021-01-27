---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Funktionen ContinuousUniformDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842321"
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

## <a name="example"></a>Exempel

Följande Q #-kodfragment ritar slumpmässigt en vinkel mellan $0 $ och $2 \pi $:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)