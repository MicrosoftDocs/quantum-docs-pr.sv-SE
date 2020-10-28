---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732174"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paketfilerna [](https://nuget.org/packages/)


Entangles två qubit-register.

Med två register, förbereder maximally Entangled State $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ mellan varje par av qubits i respektive register, förutsatt att varje register startar i $-\ket{0\cdots 0} $-tillstånd.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State


### <a name="right--qubit"></a>höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En qubit-matris i $ \ket{0\cdots $ State



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

