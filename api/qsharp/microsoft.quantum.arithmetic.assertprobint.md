---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843408"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="75d39-102">AssertProbInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="75d39-102">AssertProbInt operation</span></span>

<span data-ttu-id="75d39-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="75d39-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="75d39-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75d39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75d39-105">Förutsätter att sannolikheten för ett enskilt tillstånd för ett Quantum-register har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="75d39-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="75d39-106">Description</span><span class="sxs-lookup"><span data-stu-id="75d39-106">Description</span></span>

<span data-ttu-id="75d39-107">Med en $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, förutsätter att sannolikheten $ | \ alpha_j | ^ 2 $ för tillstånd $ \ket{j} $ som har indexerats av $j $ har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="75d39-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="75d39-108">Indata</span><span class="sxs-lookup"><span data-stu-id="75d39-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="75d39-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75d39-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75d39-110">Index $j $ för tillstånd $ \ket{j} $ som representeras av ett `LittleEndian` register.</span><span class="sxs-lookup"><span data-stu-id="75d39-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="75d39-111">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75d39-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75d39-112">Det förväntade värdet för $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="75d39-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="75d39-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="75d39-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="75d39-114">Qubit-register som lagrar $ \ket{\psi} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="75d39-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="75d39-115">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75d39-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75d39-116">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="75d39-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75d39-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75d39-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="75d39-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="75d39-118">Example</span></span>

<span data-ttu-id="75d39-119">Anta att `qubits` registret kodar ett 3-qubit Quantum-tillstånd $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {6} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="75d39-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="75d39-120">Det innebär att antalet tillstånd $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ och $ \ket \equiv\ket {6} \ket \ket {0} {1} {1} $.</span><span class="sxs-lookup"><span data-stu-id="75d39-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="75d39-121">Följande kontroller lyckades:</span><span class="sxs-lookup"><span data-stu-id="75d39-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```