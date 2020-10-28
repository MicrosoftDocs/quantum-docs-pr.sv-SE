---
uid: Microsoft.Quantum.Canon.DelayA
title: Åtgärden fördröja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728755"
---
# <a name="delaya-operation"></a>Åtgärden fördröja

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar en viss åtgärd med en fördröjning.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Beskrivning

Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.
I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.
Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .

## <a name="input"></a>Indata

### <a name="op--t--unit-adj"></a>OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

En åtgärd som ska tillämpas.


### <a name="arg--t"></a>arg: ' t

De indatatyper som åtgärden tillämpas på.


### <a name="aux--unit"></a>AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)

Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska fördröjas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. fördröjt](xref:Microsoft.Quantum.Canon.Delayed)