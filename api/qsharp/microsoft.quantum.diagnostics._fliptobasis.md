---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727405"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="61c73-102">_flipToBasis åtgärd</span><span class="sxs-lookup"><span data-stu-id="61c73-102">_flipToBasis operation</span></span>

<span data-ttu-id="61c73-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="61c73-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="61c73-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61c73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61c73-105">Tillämpar unitaries som mappar $ \ket {0} \otimes\cdots\ket {0} $ till $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, där $ \ket{\ psi_k} $ är beroende av `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="61c73-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="61c73-106">Korrespondensen mellan värdet `basis[k]` och $ \ket{\ psi_k} $ är följande:</span><span class="sxs-lookup"><span data-stu-id="61c73-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="61c73-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="61c73-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="61c73-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="61c73-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="61c73-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="61c73-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="61c73-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate of Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="61c73-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="61c73-111">Indata</span><span class="sxs-lookup"><span data-stu-id="61c73-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="61c73-112">bas: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="61c73-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="61c73-113">Matris med ID: n för enskild qubit-basis (0 <= ID <= 3), ett för varje element i qubits.</span><span class="sxs-lookup"><span data-stu-id="61c73-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="61c73-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="61c73-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="61c73-115">Qubit som ska användas.</span><span class="sxs-lookup"><span data-stu-id="61c73-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61c73-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61c73-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

