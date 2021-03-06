---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854365"
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

