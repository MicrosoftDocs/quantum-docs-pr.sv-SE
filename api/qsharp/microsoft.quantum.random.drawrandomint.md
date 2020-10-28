---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733595"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Ritar ett slumpmässigt heltal i ett angivet inklusivt intervall.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Indata

### <a name="min--int"></a>min: [heltal](xref:microsoft.quantum.lang-ref.int)

Det minsta heltal som ska ritas.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Det största heltal som ska ritas.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)