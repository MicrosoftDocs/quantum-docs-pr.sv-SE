---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729265"
---
# <a name="applytoelementa-operation"></a>ApplyToElementA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar en åtgärd på ett angivet element i en matris.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Beskrivning

En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .

## <a name="input"></a>Indata

### <a name="op--t--unit-adj"></a>OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

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
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)