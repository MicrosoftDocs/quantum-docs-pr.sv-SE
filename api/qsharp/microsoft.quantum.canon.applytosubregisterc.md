---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729058"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="6ecde-102">ApplyToSubregisterC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6ecde-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="6ecde-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ecde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ecde-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ecde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ecde-105">Tillämpar en åtgärd på ett under register i ett register, där qubits anges av en matris med sina index.</span><span class="sxs-lookup"><span data-stu-id="6ecde-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="6ecde-106">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="6ecde-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6ecde-107">Indata</span><span class="sxs-lookup"><span data-stu-id="6ecde-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="6ecde-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="6ecde-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6ecde-109">Åtgärd att tillämpa på under registrering.</span><span class="sxs-lookup"><span data-stu-id="6ecde-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="6ecde-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ecde-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6ecde-111">En matris med index som anger vilka qubits som åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="6ecde-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6ecde-112">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ecde-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ecde-113">Registrera på vilken åtgärden fungerar.</span><span class="sxs-lookup"><span data-stu-id="6ecde-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ecde-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ecde-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6ecde-115">Se även</span><span class="sxs-lookup"><span data-stu-id="6ecde-115">See Also</span></span>

- [<span data-ttu-id="6ecde-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="6ecde-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)