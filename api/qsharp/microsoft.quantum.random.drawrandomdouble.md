---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733211"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)