---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729286"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="1b90b-102">ApplyToEachIndexA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1b90b-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="1b90b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b90b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b90b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b90b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b90b-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="1b90b-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="1b90b-106">Modifieraren `A` anger att en qubit-åtgärd är adjointable.</span><span class="sxs-lookup"><span data-stu-id="1b90b-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1b90b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="1b90b-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="1b90b-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="1b90b-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1b90b-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="1b90b-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="1b90b-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="1b90b-110">register : 'T[]</span></span>

<span data-ttu-id="1b90b-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="1b90b-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b90b-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b90b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1b90b-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1b90b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b90b-114">Inte</span><span class="sxs-lookup"><span data-stu-id="1b90b-114">'T</span></span>

<span data-ttu-id="1b90b-115">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="1b90b-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b90b-116">Se även</span><span class="sxs-lookup"><span data-stu-id="1b90b-116">See Also</span></span>

- [<span data-ttu-id="1b90b-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="1b90b-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)