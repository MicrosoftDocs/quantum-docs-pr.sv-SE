---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729568"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Använder en av två enhetliga åtgärder, beroende på värdet för en klassisk bit.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a>Beskrivning

Med en bit `bit` , använder åtgärden `trueOp` med `trueInput` som indatatyp när `bit` är `true` , och gäller `falseOp(falseInput)` när `bit` är `false` .

## <a name="input"></a>Indata

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Det booleska värde som används för att avgöra om `trueOp` eller `falseOp` används.


### <a name="trueop--t--unit-adj--ctl"></a>trueOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

Den enhetliga åtgärd som ska tillämpas när `bit` är `true` .


### <a name="trueinput--t"></a>trueInput: ' t

Indata som ska anges till `trueOp` när `bit` är `true` .


### <a name="falseop--u--unit-adj--ctl"></a>falseOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

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