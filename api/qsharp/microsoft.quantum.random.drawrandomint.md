---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192918"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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