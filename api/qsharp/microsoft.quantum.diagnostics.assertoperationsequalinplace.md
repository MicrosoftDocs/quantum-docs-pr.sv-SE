---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727330"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="25d72-102">AssertOperationsEqualInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="25d72-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="25d72-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="25d72-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="25d72-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25d72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25d72-105">Två åtgärder förutsätter att de fungerar identiskt för alla ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="25d72-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="25d72-106">Den här kontrollen implementeras genom att kontrol lera åtgärdens åtgärder på alla stater i formuläret $V _0 \otimes... \otimes V_ {n-1} $, där $V _k $ är ett av tillstånden $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ och $ \ket{i} $ (+ 1 Eigenstate av Pauli Y-operatorn).</span><span class="sxs-lookup"><span data-stu-id="25d72-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="25d72-107">Den här kontrollen använder $n $ qubits och kräver flera anrop av de åtgärder som jämförs.</span><span class="sxs-lookup"><span data-stu-id="25d72-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="25d72-108">Indata</span><span class="sxs-lookup"><span data-stu-id="25d72-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="25d72-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25d72-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25d72-110">Antalet qubits-$n $ som driften `givenU` och `expectedU` arbetar med.</span><span class="sxs-lookup"><span data-stu-id="25d72-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="25d72-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25d72-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="25d72-112">Åtgärden på $n $ qubits ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="25d72-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="25d72-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="25d72-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="25d72-114">Referens åtgärd på $n $ qubits som ska `givenU` jämföras med.</span><span class="sxs-lookup"><span data-stu-id="25d72-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25d72-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25d72-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="25d72-116">Referenser</span><span class="sxs-lookup"><span data-stu-id="25d72-116">References</span></span>

<span data-ttu-id="25d72-117">Grunden för tillstånden $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ och $ \ket{i} $ är Chuang-Nielsen basen, som beskrivs i [ *. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="25d72-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="25d72-118">Se även</span><span class="sxs-lookup"><span data-stu-id="25d72-118">See Also</span></span>

- [<span data-ttu-id="25d72-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="25d72-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)