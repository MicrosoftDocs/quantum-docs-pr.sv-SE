---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852535"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en matris med åtgärder som styrs av en matris med tal tillstånd.

Det vill säga använder en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av $n $-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="unitaries--t--unit--is-adj--ctl"></a>unitaries: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []

Matris med upp till $2 ^ n $-åtgärder. $J $ th indexeras av Number State $ \ket{j} $ som kodats i litet endian-format.


### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.


### <a name="target--t"></a>mål: ' t

Allmän qubit-registrering som $V _j $ agerar på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

`coefficients` fylls i med identitets element om färre än $2 ^ n $ anges. Den här implementeringen använder $n-$1-hjälp qubits.

## <a name="references"></a>Referenser

- Mot den första Quantum-simuleringen med Quantum SpeedUp Andrew M. Children, Dmitri Maslov, Yunseongt, Neil J. Värskogsnätverksväxling, Yuan Su https://arxiv.org/abs/1711.10980