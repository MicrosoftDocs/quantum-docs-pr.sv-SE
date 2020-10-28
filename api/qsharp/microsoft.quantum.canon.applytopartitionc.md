---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729106"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="19989-102">ApplyToPartitionC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="19989-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="19989-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19989-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19989-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19989-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19989-105">Använder ett åtgärds par för en viss partition av ett register i två delar.</span><span class="sxs-lookup"><span data-stu-id="19989-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="19989-106">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="19989-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="19989-107">Indata</span><span class="sxs-lookup"><span data-stu-id="19989-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="19989-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="19989-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="19989-109">Det par med åtgärder som ska tillämpas på den aktuella partitionen.</span><span class="sxs-lookup"><span data-stu-id="19989-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="19989-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19989-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19989-111">Antalet qubits från målet som ska läggas till i den första delen av partitionen.</span><span class="sxs-lookup"><span data-stu-id="19989-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="19989-112">Återstående qubits utgör den andra delen av partitionen.</span><span class="sxs-lookup"><span data-stu-id="19989-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="19989-113">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19989-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19989-114">Ett register över qubits som är partitionerade och drivs av de två åtgärder som anges.</span><span class="sxs-lookup"><span data-stu-id="19989-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19989-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19989-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="19989-116">Se även</span><span class="sxs-lookup"><span data-stu-id="19989-116">See Also</span></span>

- [<span data-ttu-id="19989-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="19989-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)