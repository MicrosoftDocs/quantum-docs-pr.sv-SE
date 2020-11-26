---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: f28cff599e06090145fac860dbaf8274c966f80a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208558"
---
# <a name="applytoheadca-operation"></a>ApplyToHeadCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på det första elementet i en matris.

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .

## <a name="input"></a>Indata

### <a name="op--t--unit--is-adj--ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som ska tillämpas.


### <a name="targets--t"></a>mål: ' t []

En matris med mål, varav den första ska tillämpas på `op` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. Quantum. Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)