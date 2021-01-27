---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852500"
---
# <a name="multiplexoperationsfromgenerator-operation"></a>MultiplexOperationsFromGenerator-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av n-qubit Number State $ \ket{j} $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är just + CTL)

En tupel där det första elementet `Int` är antalet unitaries $N $, och det andra elementet `(Int -> ('T => () is Adj + Ctl))` är en funktion som tar ett heltal $j $ i $ [0, N-1] $ och utvärderar den enhetliga åtgärden $V _J $.


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

- [*Andrew M. Children, Dmitri Maslov, Yunseong, Neil J. värskogsnätverksväxling, Yuan Su*, arXiv: 1711.10980](https://arxiv.org/abs/1711.10980)