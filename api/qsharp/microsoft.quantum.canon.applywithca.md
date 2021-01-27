---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: a5ce7dc5ddfbb2fc06743d36614129c371850da2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841146"
---
# <a name="applywithca-operation"></a>ApplyWithCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med två åtgärder används en som konjugaten med den andra.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $. Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.

## <a name="input"></a>Indata

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just

Åtgärden $U $ som ska användas för att konjugata $V $. Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

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

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)