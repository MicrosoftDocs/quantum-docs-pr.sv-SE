---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727330"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Två åtgärder förutsätter att de fungerar identiskt för alla ingångs tillstånd.

Den här kontrollen implementeras genom att kontrol lera åtgärdens åtgärder på alla stater i formuläret $V _0 \otimes... \otimes V_ {n-1} $, där $V _k $ är ett av tillstånden $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ och $ \ket{i} $ (+ 1 Eigenstate av Pauli Y-operatorn).

Den här kontrollen använder $n $ qubits och kräver flera anrop av de åtgärder som jämförs.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits-$n $ som driften `givenU` och `expectedU` arbetar med.


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden på $n $ qubits ska kontrol leras.


### <a name="expectedu--qubit--unit-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

Referens åtgärd på $n $ qubits som ska `givenU` jämföras med.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

Grunden för tillstånden $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ och $ \ket{i} $ är Chuang-Nielsen basen, som beskrivs i [ *. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)