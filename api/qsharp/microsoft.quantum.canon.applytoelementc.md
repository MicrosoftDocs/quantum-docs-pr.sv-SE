---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850746"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på ett angivet element i en matris.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Description

En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .

## <a name="input"></a>Indata

### <a name="op--t--unit--is-ctl"></a>OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL

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