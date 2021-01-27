---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851146"
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

## <a name="example"></a>Exempel

Följande Q #-kodfragment rullar slumpmässigt en sida med sex sidor:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Kommentarer

Miss lyckas om `max <= min` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)