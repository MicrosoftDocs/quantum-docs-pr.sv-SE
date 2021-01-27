---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5159eee07f7398cc6194c9907a37b78a63aaf263
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850782"
---
# <a name="applytoelement-operation"></a>ApplyToElement-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på ett angivet element i en matris.

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Description

En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .

## <a name="input"></a>Indata

### <a name="op--t--unit"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)