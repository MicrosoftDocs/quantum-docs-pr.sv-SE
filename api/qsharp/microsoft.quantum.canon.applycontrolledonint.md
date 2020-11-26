---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219013"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en enhetlig åtgärd i mål registret om status för kontroll registret motsvarar ett angivet positivt heltal.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Ett icke-negativt heltal som åtgärden `oracle` ska kontrol leras på.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En enhetlig åtgärd som ska kontrol leras.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett Quantum-register som styr programmet för `oracle` .


### <a name="targetregister--t"></a>targetRegister: ' t

En register som ska tillämpas på `oracle` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Värdet för `numberState` tolkas med en lite-endian-kodning.

`numberState` måste vara högst $2 ^ \texttt{Length (controlRegister)}-$1.
Det kan till exempel `numberState = 537` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {537} $.