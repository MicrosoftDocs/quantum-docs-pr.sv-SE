---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219115"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="f2bec-102">ApplyCNOTChainWithTarget-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f2bec-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="f2bec-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2bec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2bec-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2bec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2bec-105">Beräknar pariteten för en matris med qubits i en mål-qubit.</span><span class="sxs-lookup"><span data-stu-id="f2bec-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f2bec-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f2bec-106">Description</span></span>

<span data-ttu-id="f2bec-107">Om matrisen inlednings vis är i läget $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, erhålls det slutliga stadiet av $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="f2bec-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="f2bec-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f2bec-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="f2bec-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2bec-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2bec-110">Matris för qubits som pariteten beräknas på.</span><span class="sxs-lookup"><span data-stu-id="f2bec-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="f2bec-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f2bec-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f2bec-112">Den slutliga qubit där pariteten för "qubits" är XORed.</span><span class="sxs-lookup"><span data-stu-id="f2bec-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2bec-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2bec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f2bec-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f2bec-114">Remarks</span></span>

<span data-ttu-id="f2bec-115">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="f2bec-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="f2bec-116">och</span><span class="sxs-lookup"><span data-stu-id="f2bec-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```