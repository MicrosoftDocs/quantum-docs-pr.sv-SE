---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206484"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd för varje index i kartesiska-kraften i ett heltals intervall.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Beskrivning

En åtgärd tillämpas iterativt för varje element i en kartesiska-potens av intervallet `0..(bound - 1)` .

## <a name="input"></a>Indata

### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Kartesiska-kraften som intervallet `0..(bound - 1)` ska höjas till.


### <a name="bound--int"></a>Bound: [int](xref:microsoft.quantum.lang-ref.int)

En specifikation av intervallet som ska upprepas, anges som längden på intervallet.


### <a name="op--int--unit"></a>OP: [int](xref:microsoft.quantum.lang-ref.int)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som ska anropas för varje element med den aktuella kartesiska-kraften.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)