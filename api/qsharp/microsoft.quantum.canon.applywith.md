---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 61047ea2ea249e5a4d39b5747c542462c9632138
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729034"
---
# <a name="applywith-operation"></a>ApplyWith-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Med två åtgärder används en som konjugaten med den andra.

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a>Beskrivning

Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $. Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.

## <a name="input"></a>Indata

### <a name="outeroperation--t--unit-adj"></a>outerOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

Åtgärden $U $ som ska användas för att konjugata $V $. Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.


### <a name="inneroperation--t--unit"></a>innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden $V $ som är konjugaten.


### <a name="target--t"></a>mål: ' t

Indata som ska tillhandahållas de yttre och inre åtgärderna.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet där var och en av de inre och yttre åtgärderna fungerar.

## <a name="remarks"></a>Kommentarer

Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)