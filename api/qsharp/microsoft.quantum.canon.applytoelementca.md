---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208864"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på ett angivet element i en matris.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .

## <a name="input"></a>Indata

### <a name="op--t--unit--is-adj--ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som ska tillämpas.


### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Ett index i matrisen med mål.


### <a name="targets--t"></a>mål: ' t []

En matris med möjliga mål för `op` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)