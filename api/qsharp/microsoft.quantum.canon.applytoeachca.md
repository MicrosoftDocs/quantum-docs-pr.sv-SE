---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729292"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="5fe7d-102">ApplyToEachCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5fe7d-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="5fe7d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5fe7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5fe7d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5fe7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5fe7d-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="5fe7d-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="5fe7d-106">Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="5fe7d-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5fe7d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="5fe7d-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="5fe7d-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="5fe7d-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5fe7d-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="5fe7d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="5fe7d-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="5fe7d-110">register : 'T[]</span></span>

<span data-ttu-id="5fe7d-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="5fe7d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fe7d-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe7d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5fe7d-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5fe7d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5fe7d-114">Inte</span><span class="sxs-lookup"><span data-stu-id="5fe7d-114">'T</span></span>

<span data-ttu-id="5fe7d-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="5fe7d-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fe7d-116">Se även</span><span class="sxs-lookup"><span data-stu-id="5fe7d-116">See Also</span></span>

- [<span data-ttu-id="5fe7d-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="5fe7d-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)