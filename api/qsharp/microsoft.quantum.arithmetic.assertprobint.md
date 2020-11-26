---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223705"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="3a45e-102">AssertProbInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3a45e-102">AssertProbInt operation</span></span>

<span data-ttu-id="3a45e-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3a45e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3a45e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a45e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a45e-105">Förutsätter att sannolikheten för ett enskilt tillstånd för ett Quantum-register har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="3a45e-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="3a45e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3a45e-106">Description</span></span>

<span data-ttu-id="3a45e-107">Med en $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, förutsätter att sannolikheten $ | \ alpha_j | ^ 2 $ för tillstånd $ \ket{j} $ som har indexerats av $j $ har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="3a45e-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="3a45e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="3a45e-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="3a45e-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a45e-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a45e-110">Index $j $ för tillstånd $ \ket{j} $ som representeras av ett `LittleEndian` register.</span><span class="sxs-lookup"><span data-stu-id="3a45e-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="3a45e-111">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a45e-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3a45e-112">Det förväntade värdet för $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="3a45e-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3a45e-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3a45e-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3a45e-114">Qubit-register som lagrar $ \ket{\psi} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="3a45e-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3a45e-115">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a45e-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3a45e-116">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="3a45e-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a45e-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a45e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

