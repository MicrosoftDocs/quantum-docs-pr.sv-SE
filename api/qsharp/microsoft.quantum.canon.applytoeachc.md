---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217789"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="bf063-102">ApplyToEachC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bf063-102">ApplyToEachC operation</span></span>

<span data-ttu-id="bf063-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf063-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf063-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf063-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf063-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="bf063-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="bf063-106">Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="bf063-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="bf063-107">Indata</span><span class="sxs-lookup"><span data-stu-id="bf063-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="bf063-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="bf063-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bf063-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="bf063-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bf063-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="bf063-110">register : 'T[]</span></span>

<span data-ttu-id="bf063-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="bf063-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf063-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf063-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf063-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bf063-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf063-114">Inte</span><span class="sxs-lookup"><span data-stu-id="bf063-114">'T</span></span>

<span data-ttu-id="bf063-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="bf063-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf063-116">Se även</span><span class="sxs-lookup"><span data-stu-id="bf063-116">See Also</span></span>

- [<span data-ttu-id="bf063-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bf063-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)