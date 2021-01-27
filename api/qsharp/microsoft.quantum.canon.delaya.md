---
uid: Microsoft.Quantum.Canon.DelayA
title: Åtgärden fördröja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c7385cfcdf782347feb8d95311205a9311f4c929
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840671"
---
# <a name="delaya-operation"></a>Åtgärden fördröja

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en viss åtgärd med en fördröjning.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a>Description

Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.
I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.
Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .

## <a name="input"></a>Indata

### <a name="op--t--unit--is-adj"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

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