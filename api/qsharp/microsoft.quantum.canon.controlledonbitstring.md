---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Funktionen ControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728818"
---
# <a name="controlledonbitstring-function"></a>Funktionen ControlledOnBitString

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Returnerar en enhetlig åtgärd som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar en angiven bitmask.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Beskrivning

Resultatet av den här funktionen är en åtgärd som kan representeras av en enhetlig omvandling $U $ t. ex. \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{IF} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} där $V $ är en enhetlig omvandling som representerar åtgärdens åtgärd `oracle` .

## <a name="input"></a>Indata

### <a name="bits--bool"></a>bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bit strängen som styr den åtgärd som åtgärdas.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

Den enhetliga åtgärd som ska tillämpas på mål registret.



## <a name="output--qubitt--unit-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], inte) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

En enhetlig åtgärd som gäller `oracle` för mål registret om status för kontroll registret motsvarar bitmask `bits` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).
Om `bits` är längre än `controlRegister` uppstår ett fel.

`bits` `oracle` Resultatet av den här funktionen är en åtgärd som utför följande steg för att få en boolesk matris och en enhetlig åtgärd:

* tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` element i `bits` .
* gäller `Controlled oracle` för kontroll-och mål registren.
* tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` elementet i `bits` igen för att returnera kontroll registret till det ursprungliga läget.

Utdata från `Controlled` Functor är ett specialfall av `ControlledOnBitString` var `bits` är lika med `[true, ..., true]` .