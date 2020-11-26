---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209493"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en av två kontrollerbara åtgärder, beroende på värdet för ett klassiskt resultat.

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Beskrivning

`result`På grund av detta tillämpas åtgärden `zeroOp` med `zeroInput` som indatamängden när `result` är lika med `Zero` , och tillämpas `oneOp(oneInput)` när `result == One` .

## <a name="input"></a>Indata

### <a name="result--__invalidresult__"></a>resultat: __ogiltigt <Result>__

Mät resultatet som används för att avgöra om `zeroOp` eller används `oneOp` .


### <a name="zeroop--t--unit--is-ctl"></a>zeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

Den kontrollerbara åtgärd som ska tillämpas när `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: ' t

Indata som ska anges till `zeroOp` när `result == Zero` .


### <a name="oneop--u--unit--is-ctl"></a>oneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

Den kontrollerbara åtgärd som ska tillämpas när `result == One` .


### <a name="oneinput--u"></a>oneInput: ' U

Indata som ska anges till `oneOp` när `result == One` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd `zeroOp` som ska tillämpas villkorligt.
### <a name="u"></a>' U

Indatatypen för den åtgärd `oneOp` som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)