---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729067"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="615d1-102">ApplyToSubregisterA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="615d1-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="615d1-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="615d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="615d1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="615d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="615d1-105">Tillämpar en åtgärd på ett under register i ett register, där qubits anges av en matris med sina index.</span><span class="sxs-lookup"><span data-stu-id="615d1-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="615d1-106">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="615d1-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="615d1-107">Indata</span><span class="sxs-lookup"><span data-stu-id="615d1-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="615d1-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="615d1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="615d1-109">Åtgärd att tillämpa på under registrering.</span><span class="sxs-lookup"><span data-stu-id="615d1-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="615d1-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="615d1-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="615d1-111">En matris med index som anger vilka qubits som åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="615d1-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="615d1-112">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="615d1-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="615d1-113">Registrera på vilken åtgärden fungerar.</span><span class="sxs-lookup"><span data-stu-id="615d1-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="615d1-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="615d1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="615d1-115">Se även</span><span class="sxs-lookup"><span data-stu-id="615d1-115">See Also</span></span>

- [<span data-ttu-id="615d1-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="615d1-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)