---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: Funktionen ConjugatedBy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c11e6b2cc97e682bf4fe266997f60ce69e87ba96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840864"
---
# <a name="conjugatedby-function"></a>Funktionen ConjugatedBy

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vissa yttre och inre åtgärder returnerar en ny åtgärd som konjugaterar den inre åtgärden med den yttre åtgärden.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Indata

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just

Åtgärden $U $ som ska användas för att konjugata $V $. Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.


### <a name="inneroperation--t--unit"></a>innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden $V $ som är konjugaten.



## <a name="output--t--unit"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd vars åtgärd representeras av den enhetliga $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen av mål där var och en av de inre och yttre åtgärderna fungerar.

## <a name="remarks"></a>Kommentarer

Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)