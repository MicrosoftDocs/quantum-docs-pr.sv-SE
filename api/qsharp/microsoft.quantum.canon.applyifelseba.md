---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844987"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en av två adjointable-åtgärder, beroende på värdet för en klassisk bit.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Description

Med en bit `bit` , använder åtgärden `trueOp` med `trueInput` som indatatyp när `bit` är `true` , och gäller `falseOp(falseInput)` när `bit` är `false` .

## <a name="input"></a>Indata

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Det booleska värde som används för att avgöra om `trueOp` eller `falseOp` används.


### <a name="trueop--t--unit--is-adj"></a>trueOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just

Den adjointable-åtgärd som ska tillämpas när `bit` är `true` .


### <a name="trueinput--t"></a>trueInput: ' t

Indata som ska anges till `trueOp` när `bit` är `true` .


### <a name="falseop--u--unit--is-adj"></a>falseOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Den adjointable-åtgärd som ska tillämpas när `bit` är `false` .


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