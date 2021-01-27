---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4ed0660e2fe3623d0a8e4e4f3bd0bddb536b7b5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844881"
---
# <a name="applyifzeroca-operation"></a>ApplyIfZeroCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en åtgärd med ett enhetligt resultat på ett klassiskt resultat värde som noll.

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` . Om `One` händer ingenting `target` .
Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).

## <a name="input"></a>Indata

### <a name="result--__invalidresult__"></a>resultat: __ogiltigt <Result>__

Ett mått resultat som styr om OP används eller inte.


### <a name="op--t--unit--is-adj--ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som ska tillämpas villkorligt.


### <a name="target--t"></a>mål: ' t

De indatatyper som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. Quantum. Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. Quantum. Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)