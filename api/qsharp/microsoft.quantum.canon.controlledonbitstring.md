---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Funktionen ControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840807"
---
# <a name="controlledonbitstring-function"></a>Funktionen ControlledOnBitString

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en enhetlig åtgärd som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar en angiven bitmask.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Description

Resultatet av den här funktionen är en åtgärd som kan representeras av en enhetlig omvandling $U $ t. ex. \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{IF} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} där $V $ är en enhetlig omvandling som representerar åtgärdens åtgärd `oracle` .

## <a name="input"></a>Indata

### <a name="bits--bool"></a>bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bit strängen som styr den åtgärd som åtgärdas.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den enhetliga åtgärd som ska tillämpas på mål registret.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En enhetlig åtgärd som gäller `oracle` för mål registret om status för kontroll registret motsvarar bitmask `bits` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="example"></a>Exempel

Följande kodfragment är likvärdiga:

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

och

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

Följande kod förbereder ett tillstånd $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Kommentarer

Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).
Om `bits` är längre än `controlRegister` uppstår ett fel.

`bits` `oracle` Resultatet av den här funktionen är en åtgärd som utför följande steg för att få en boolesk matris och en enhetlig åtgärd:

* tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` element i `bits` .
* gäller `Controlled oracle` för kontroll-och mål registren.
* tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` elementet i `bits` igen för att returnera kontroll registret till det ursprungliga läget.

Utdata från `Controlled` Functor är ett specialfall av `ControlledOnBitString` var `bits` är lika med `[true, ..., true]` .