---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Mått åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818776"
---
# <a name="measure-operation"></a>Mått åtgärd

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Utför en gemensam mätning av en eller flera qubits i de angivna Pauli-baserna.

Resultatet av utdata anges av fördelningen: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} där $P _i $ är $i $ th-elementet `bases` och där $N = \texttt{Length} (\texttt{Bases}) $.
Det vill säga att måttet returnerar en `Result` $d $ så att eigenvalue för den observerade mått resultatet är $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Indata

### <a name="bases--pauli"></a>Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matris med qubit Pauli-värden som indikerar betalares produkt faktorer på varje qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera qubits som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

`Zero` om $ + $1-eigenvalue observeras och `One` om $-$1-eigenvalue observeras.

## <a name="remarks"></a>Kommentarer

Om bas mat ris-och qubit-matrisen har olika längd kommer åtgärden att Miss sen.