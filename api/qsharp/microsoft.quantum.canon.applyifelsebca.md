---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844961"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en av två enhetliga åtgärder, beroende på värdet för en klassisk bit.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Med en bit `bit` , använder åtgärden `trueOp` med `trueInput` som indatatyp när `bit` är `true` , och gäller `falseOp(falseInput)` när `bit` är `false` .

## <a name="input"></a>Indata

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Det booleska värde som används för att avgöra om `trueOp` eller `falseOp` används.


### <a name="trueop--t--unit--is-adj--ctl"></a>trueOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den enhetliga åtgärd som ska tillämpas när `bit` är `true` .


### <a name="trueinput--t"></a>trueInput: ' t

Indata som ska anges till `trueOp` när `bit` är `true` .


### <a name="falseop--u--unit--is-adj--ctl"></a>falseOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den enhetliga åtgärd som ska tillämpas när `bit` är `false` .


### <a name="falseinput--u"></a>falseInput: ' U

Indata som ska anges till `falseOp` när `bit` är `false` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd `trueOp` som ska tillämpas villkorligt.
### <a name="u"></a>' U

Indatatypen för den åtgärd `falseOp` som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)