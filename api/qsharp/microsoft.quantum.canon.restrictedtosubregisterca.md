---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: Funktionen RestrictedToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728425"
---
# <a name="restrictedtosubregisterca-function"></a><span data-ttu-id="d1885-102">Funktionen RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="d1885-102">RestrictedToSubregisterCA function</span></span>

<span data-ttu-id="d1885-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1885-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1885-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1885-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1885-105">Begränsar en åtgärd till en matris med index i ett register, dvs. en under registrering.</span><span class="sxs-lookup"><span data-stu-id="d1885-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="d1885-106">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="d1885-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d1885-107">Indata</span><span class="sxs-lookup"><span data-stu-id="d1885-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="d1885-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="d1885-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d1885-109">Åtgärd som ska begränsas till en under registrering.</span><span class="sxs-lookup"><span data-stu-id="d1885-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="d1885-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d1885-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d1885-111">En matris med index som anger vilka qubits som åtgärden ska begränsas till.</span><span class="sxs-lookup"><span data-stu-id="d1885-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="d1885-112">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="d1885-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="d1885-113">Se även</span><span class="sxs-lookup"><span data-stu-id="d1885-113">See Also</span></span>

- [<span data-ttu-id="d1885-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="d1885-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)