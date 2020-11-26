---
uid: Microsoft.Quantum.Intrinsic.Exp
title: EXP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212417"
---
# <a name="exp-operation"></a><span data-ttu-id="f6442-102">EXP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f6442-102">Exp operation</span></span>

<span data-ttu-id="f6442-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f6442-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f6442-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f6442-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f6442-105">Använder exponenten för en multi-qubit Pauli-operator.</span><span class="sxs-lookup"><span data-stu-id="f6442-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="f6442-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} där $P _i $ är $i $ th-elementet i `paulis` och där $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="f6442-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f6442-107">Indata</span><span class="sxs-lookup"><span data-stu-id="f6442-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="f6442-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="f6442-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="f6442-109">Matris med qubit Pauli-värden som indikerar betalares produkt faktorer på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="f6442-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="f6442-110">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6442-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6442-111">Vinkeln för den angivna multi-qubit Pauli-operatorn som mål registret ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="f6442-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f6442-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f6442-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f6442-113">Registrera dig för att tillämpa den aktuella rotationen på.</span><span class="sxs-lookup"><span data-stu-id="f6442-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f6442-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6442-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

