---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210479"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entangles två qubit-register.

Med två register, förbereder maximally Entangled State $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ mellan varje par av qubits i respektive register, förutsatt att varje register startar i $-\ket{0\cdots 0} $-tillstånd.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State


### <a name="right--qubit"></a>höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

