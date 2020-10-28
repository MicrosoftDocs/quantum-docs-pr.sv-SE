---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727399"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Med två register, förbereder maximally Entangled-statusen mellan varje par av qubits i respektive register.
Alla qubits måste starta i ⟩-läget | 0.

Resultatet är att motsvarande par qubits från varje register finns i $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State


### <a name="right--qubit"></a>höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

