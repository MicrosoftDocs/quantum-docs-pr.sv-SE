---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726694"
---
# <a name="expfrac-operation"></a>ExpFrac-åtgärd

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paketfilerna [](https://nuget.org/packages/)


Använder exponenten för en multi-qubit Pauli-operator med ett argument som angetts av en dyadic-fraktion.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} där $P _i $ är $i $ th-elementet i `paulis` och där $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matris med qubit Pauli-värden som indikerar betalares produkt faktorer på varje qubit.


### <a name="numerator--int"></a>täljare: [int](xref:microsoft.quantum.lang-ref.int)

Täljare ($k $) i dyadic fraktions representation av den vinkel som qubit-registret ska roteras med.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Kraften hos två ($n $) som anger nämnaren för den vinkel som qubit-registret ska roteras med.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig för att tillämpa den aktuella rotationen på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

