---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729277"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="6591a-102">ApplyToEachIndexCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6591a-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="6591a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6591a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6591a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6591a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6591a-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="6591a-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6591a-106">Modifieraren `CA` anger att en qubit-åtgärd är adjointable och kan kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="6591a-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6591a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="6591a-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="6591a-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="6591a-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6591a-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="6591a-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6591a-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="6591a-110">register : 'T[]</span></span>

<span data-ttu-id="6591a-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="6591a-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6591a-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6591a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6591a-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6591a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6591a-114">Inte</span><span class="sxs-lookup"><span data-stu-id="6591a-114">'T</span></span>

<span data-ttu-id="6591a-115">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="6591a-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6591a-116">Se även</span><span class="sxs-lookup"><span data-stu-id="6591a-116">See Also</span></span>

- [<span data-ttu-id="6591a-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="6591a-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)