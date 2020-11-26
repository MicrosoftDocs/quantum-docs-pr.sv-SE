---
uid: Microsoft.Quantum.Canon.Delay
title: Fördröjnings åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216514"
---
# <a name="delay-operation"></a>Fördröjnings åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en viss åtgärd med en fördröjning.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Beskrivning

Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.
I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.
Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .

## <a name="input"></a>Indata

### <a name="op--t--u"></a>OP: t => ' U 

En åtgärd som ska tillämpas.


### <a name="arg--t"></a>arg: ' t

De indatatyper som åtgärden tillämpas på.


### <a name="aux--unit"></a>AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)

Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.



## <a name="output--u"></a>Utdata: ' U



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska fördröjas.
### <a name="u"></a>' U

Retur typen för åtgärden som ska fördröjas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. Quantum. Canon. Delaya](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Quantum. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. Quantum. Canon. fördröjt](xref:Microsoft.Quantum.Canon.Delayed)