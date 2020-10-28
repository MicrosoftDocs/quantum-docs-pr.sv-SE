---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729250"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar en åtgärd på ett angivet element i en matris.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Beskrivning

En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .

## <a name="input"></a>Indata

### <a name="op--t--unit-ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL

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
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)