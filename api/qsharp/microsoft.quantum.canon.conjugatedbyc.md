---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: Funktionen ConjugatedByC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 622b1d93dcbd02d000a68de23c66537b24d36c99
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840844"
---
# <a name="conjugatedbyc-function"></a>Funktionen ConjugatedByC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vissa yttre och inre åtgärder returnerar en ny åtgärd som konjugaterar den inre åtgärden med den yttre åtgärden.

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just

Åtgärden $U $ som ska användas för att konjugata $V $. Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.


### <a name="inneroperation--t--unit--is-ctl"></a>innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

Åtgärden $V $ som är konjugaten.



## <a name="output--t--unit--is-ctl"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd vars åtgärd representeras av den enhetliga $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen av mål där var och en av de inre och yttre åtgärderna fungerar.

## <a name="remarks"></a>Kommentarer

Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ConjugatedBy](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)