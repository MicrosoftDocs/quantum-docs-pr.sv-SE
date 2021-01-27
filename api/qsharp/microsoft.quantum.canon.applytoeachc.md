---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850842"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="680ff-102">ApplyToEachC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="680ff-102">ApplyToEachC operation</span></span>

<span data-ttu-id="680ff-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="680ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="680ff-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="680ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="680ff-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="680ff-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="680ff-106">Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="680ff-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="680ff-107">Indata</span><span class="sxs-lookup"><span data-stu-id="680ff-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="680ff-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="680ff-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="680ff-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="680ff-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="680ff-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="680ff-110">register : 'T[]</span></span>

<span data-ttu-id="680ff-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="680ff-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="680ff-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="680ff-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="680ff-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="680ff-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="680ff-114">Inte</span><span class="sxs-lookup"><span data-stu-id="680ff-114">'T</span></span>

<span data-ttu-id="680ff-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="680ff-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="680ff-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="680ff-116">Example</span></span>

<span data-ttu-id="680ff-117">Förbered ett tre-qubit $ \ket{+} $-tillstånd:</span><span class="sxs-lookup"><span data-stu-id="680ff-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="680ff-118">Se även</span><span class="sxs-lookup"><span data-stu-id="680ff-118">See Also</span></span>

- [<span data-ttu-id="680ff-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="680ff-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)