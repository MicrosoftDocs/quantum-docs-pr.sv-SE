---
uid: Microsoft.Quantum.Canon.DelayedC
title: Funktionen DelayedC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840567"
---
# <a name="delayedc-function"></a>Funktionen DelayedC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="op--t--unit--is-ctl"></a>OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL

En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas


### <a name="arg--t"></a>arg: ' t

De indatatyper som åtgärden `op` tillämpas på.



## <a name="output--unit--unit--is-ctl"></a>Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd som gäller `op` för inmatade `arg`

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska fördröjas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. fördröjt](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)