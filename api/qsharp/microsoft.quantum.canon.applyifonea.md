---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844934"
---
# <a name="applyifonea-operation"></a>ApplyIfOneA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en adjointable-åtgärd som har ett klassiskt resultat värde som ett.

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a>Description

En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` . Om `Zero` händer ingenting `target` .
Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.

## <a name="input"></a>Indata

### <a name="result--__invalidresult__"></a>resultat: __ogiltigt <Result>__

Ett mått resultat som styr om OP används eller inte.


### <a name="op--t--unit--is-adj"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En åtgärd som ska tillämpas villkorligt.


### <a name="target--t"></a>mål: ' t

De indatatyper som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Quantum. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. Quantum. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)