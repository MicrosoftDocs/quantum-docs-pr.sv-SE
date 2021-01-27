---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: d46c42846066befafda2af22f7b6e861cb260c33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831014"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="5a034-102">_flipToBasis åtgärd</span><span class="sxs-lookup"><span data-stu-id="5a034-102">_flipToBasis operation</span></span>

<span data-ttu-id="5a034-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5a034-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5a034-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5a034-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5a034-105">Tillämpar unitaries som mappar $ \ket {0} \otimes\cdots\ket {0} $ till $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, där $ \ket{\ psi_k} $ är beroende av `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="5a034-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="5a034-106">Korrespondensen mellan värdet `basis[k]` och $ \ket{\ psi_k} $ är följande:</span><span class="sxs-lookup"><span data-stu-id="5a034-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="5a034-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="5a034-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="5a034-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="5a034-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="5a034-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="5a034-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="5a034-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate of Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="5a034-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a034-111">Indata</span><span class="sxs-lookup"><span data-stu-id="5a034-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="5a034-112">bas: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5a034-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5a034-113">Matris med ID: n för enskild qubit-basis (0 <= ID <= 3), ett för varje element i qubits.</span><span class="sxs-lookup"><span data-stu-id="5a034-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5a034-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5a034-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5a034-115">Qubit som ska användas.</span><span class="sxs-lookup"><span data-stu-id="5a034-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a034-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a034-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

