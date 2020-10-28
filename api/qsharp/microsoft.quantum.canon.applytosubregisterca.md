---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729052"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="d7ea6-102">ApplyToSubregisterCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d7ea6-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="d7ea6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7ea6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7ea6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7ea6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7ea6-105">Tillämpar en åtgärd på ett under register i ett register, där qubits anges av en matris med sina index.</span><span class="sxs-lookup"><span data-stu-id="d7ea6-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="d7ea6-106">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="d7ea6-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d7ea6-107">Indata</span><span class="sxs-lookup"><span data-stu-id="d7ea6-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="d7ea6-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="d7ea6-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d7ea6-109">Åtgärd att tillämpa på under registrering.</span><span class="sxs-lookup"><span data-stu-id="d7ea6-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="d7ea6-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d7ea6-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d7ea6-111">En matris med index som anger vilka qubits som åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="d7ea6-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d7ea6-112">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d7ea6-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d7ea6-113">Registrera på vilken åtgärden fungerar.</span><span class="sxs-lookup"><span data-stu-id="d7ea6-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7ea6-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7ea6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d7ea6-115">Se även</span><span class="sxs-lookup"><span data-stu-id="d7ea6-115">See Also</span></span>

- [<span data-ttu-id="d7ea6-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="d7ea6-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)