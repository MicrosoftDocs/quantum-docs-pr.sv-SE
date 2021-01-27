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
# <a name="measure-operation"></a><span data-ttu-id="51f11-102">Mått åtgärd</span><span class="sxs-lookup"><span data-stu-id="51f11-102">Measure operation</span></span>

<span data-ttu-id="51f11-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="51f11-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="51f11-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="51f11-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="51f11-105">Utför en gemensam mätning av en eller flera qubits i de angivna Pauli-baserna.</span><span class="sxs-lookup"><span data-stu-id="51f11-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="51f11-106">Resultatet av utdata anges av fördelningen: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} där $P _i $ är $i $ th-elementet `bases` och där $N = \texttt{Length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="51f11-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="51f11-107">Det vill säga att måttet returnerar en `Result` $d $ så att eigenvalue för den observerade mått resultatet är $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="51f11-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="51f11-108">Indata</span><span class="sxs-lookup"><span data-stu-id="51f11-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="51f11-109">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="51f11-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="51f11-110">Matris med qubit Pauli-värden som indikerar betalares produkt faktorer på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="51f11-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="51f11-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="51f11-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="51f11-112">Registrera qubits som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="51f11-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="51f11-113">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="51f11-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="51f11-114">`Zero` om $ + $1-eigenvalue observeras och `One` om $-$1-eigenvalue observeras.</span><span class="sxs-lookup"><span data-stu-id="51f11-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="51f11-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="51f11-115">Remarks</span></span>

<span data-ttu-id="51f11-116">Om bas mat ris-och qubit-matrisen har olika längd kommer åtgärden att Miss sen.</span><span class="sxs-lookup"><span data-stu-id="51f11-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>