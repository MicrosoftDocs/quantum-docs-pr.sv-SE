---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219081"
---
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en enhetlig åtgärd i mål registret, som kontrol leras i ett tillstånd som anges av en viss bitmask.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="bits--bool"></a>bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bit strängen som styr den åtgärd som åtgärdas.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den enhetliga åtgärd som ska tillämpas på mål registret.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett Quantum-register som styr programmet för `oracle` .


### <a name="targetregister--t"></a>targetRegister: ' t

Mål registret som ska skickas till `oracle` som inmatade.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).
Om `bits` är längre än `controlRegister` uppstår ett fel.

Det kan till exempel `bits = [0,1,0,0,1]` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.