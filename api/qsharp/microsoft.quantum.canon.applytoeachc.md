---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729298"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="bfc47-102">ApplyToEachC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bfc47-102">ApplyToEachC operation</span></span>

<span data-ttu-id="bfc47-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfc47-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfc47-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfc47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfc47-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="bfc47-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="bfc47-106">Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="bfc47-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bfc47-107">Indata</span><span class="sxs-lookup"><span data-stu-id="bfc47-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="bfc47-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="bfc47-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bfc47-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="bfc47-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bfc47-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="bfc47-110">register : 'T[]</span></span>

<span data-ttu-id="bfc47-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="bfc47-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bfc47-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfc47-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bfc47-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bfc47-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfc47-114">Inte</span><span class="sxs-lookup"><span data-stu-id="bfc47-114">'T</span></span>

<span data-ttu-id="bfc47-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="bfc47-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfc47-116">Se även</span><span class="sxs-lookup"><span data-stu-id="bfc47-116">See Also</span></span>

- [<span data-ttu-id="bfc47-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bfc47-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)