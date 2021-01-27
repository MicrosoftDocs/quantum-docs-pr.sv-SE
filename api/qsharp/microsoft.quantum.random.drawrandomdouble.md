---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847612"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Ritar ett slumpmässigt reellt tal i ett angivet inklusiv-intervall.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Indata

### <a name="min--double"></a>min: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det minsta reella tal som ska ritas.


### <a name="max--double"></a>Max: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det största reella tal som ska ritas.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Ett slumpmässigt reellt tal i inkluderar-intervallet från `min` till `max` med enhetlig sannolikhet.

## <a name="example"></a>Exempel

Följande Q #-kodfragment ritar slumpmässigt en vinkel mellan $0 $ och $2 \pi $:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)