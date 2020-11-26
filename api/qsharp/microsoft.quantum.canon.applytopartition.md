---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: f36bccb727bb38a0cdf4f1fedabc9f3f554059ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208405"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="9e2c4-102">ApplyToPartition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9e2c4-102">ApplyToPartition operation</span></span>

<span data-ttu-id="9e2c4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e2c4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e2c4-105">Använder ett åtgärds par för en viss partition av ett register i två delar.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9e2c4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9e2c4-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="9e2c4-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9e2c4-108">Det par med åtgärder som ska tillämpas på den aktuella partitionen.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="9e2c4-109">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e2c4-110">Antalet qubits från målet som ska läggas till i den första delen av partitionen.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="9e2c4-111">Återstående qubits utgör den andra delen av partitionen.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9e2c4-112">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9e2c4-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9e2c4-113">Ett register över qubits som är partitionerade och drivs av de två åtgärder som anges.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e2c4-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9e2c4-115">Se även</span><span class="sxs-lookup"><span data-stu-id="9e2c4-115">See Also</span></span>

- [<span data-ttu-id="9e2c4-116">Microsoft. Quantum. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="9e2c4-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="9e2c4-117">Microsoft. Quantum. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="9e2c4-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="9e2c4-118">Microsoft. Quantum. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="9e2c4-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)