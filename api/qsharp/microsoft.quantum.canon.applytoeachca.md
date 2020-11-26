---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217755"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="8657c-102">ApplyToEachCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8657c-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="8657c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8657c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8657c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8657c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8657c-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="8657c-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="8657c-106">Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="8657c-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8657c-107">Indata</span><span class="sxs-lookup"><span data-stu-id="8657c-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="8657c-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="8657c-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8657c-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="8657c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="8657c-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="8657c-110">register : 'T[]</span></span>

<span data-ttu-id="8657c-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="8657c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8657c-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8657c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8657c-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8657c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8657c-114">Inte</span><span class="sxs-lookup"><span data-stu-id="8657c-114">'T</span></span>

<span data-ttu-id="8657c-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="8657c-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="8657c-116">Se även</span><span class="sxs-lookup"><span data-stu-id="8657c-116">See Also</span></span>

- [<span data-ttu-id="8657c-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="8657c-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)