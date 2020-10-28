---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Funktionen RestrictedToSubregisterA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728428"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="14f10-102">Funktionen RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="14f10-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="14f10-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14f10-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14f10-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14f10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14f10-105">Begränsar en åtgärd till en matris med index i ett register, dvs. en under registrering.</span><span class="sxs-lookup"><span data-stu-id="14f10-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="14f10-106">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="14f10-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="14f10-107">Indata</span><span class="sxs-lookup"><span data-stu-id="14f10-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="14f10-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="14f10-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="14f10-109">Åtgärd som ska begränsas till en under registrering.</span><span class="sxs-lookup"><span data-stu-id="14f10-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="14f10-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14f10-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14f10-111">En matris med index som anger vilka qubits som åtgärden ska begränsas till.</span><span class="sxs-lookup"><span data-stu-id="14f10-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj"></a><span data-ttu-id="14f10-112">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="14f10-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="14f10-113">Se även</span><span class="sxs-lookup"><span data-stu-id="14f10-113">See Also</span></span>

- [<span data-ttu-id="14f10-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="14f10-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)