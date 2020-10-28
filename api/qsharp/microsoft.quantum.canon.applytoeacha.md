---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729304"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="0a49f-102">ApplyToEachA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0a49f-102">ApplyToEachA operation</span></span>

<span data-ttu-id="0a49f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a49f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a49f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a49f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a49f-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="0a49f-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="0a49f-106">Modifieraren `A` anger att en qubit-åtgärd är adjointable.</span><span class="sxs-lookup"><span data-stu-id="0a49f-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0a49f-107">Indata</span><span class="sxs-lookup"><span data-stu-id="0a49f-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="0a49f-108">singleElementOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="0a49f-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0a49f-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="0a49f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="0a49f-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="0a49f-110">register : 'T[]</span></span>

<span data-ttu-id="0a49f-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="0a49f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a49f-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a49f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0a49f-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0a49f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a49f-114">Inte</span><span class="sxs-lookup"><span data-stu-id="0a49f-114">'T</span></span>

<span data-ttu-id="0a49f-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="0a49f-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a49f-116">Se även</span><span class="sxs-lookup"><span data-stu-id="0a49f-116">See Also</span></span>

- [<span data-ttu-id="0a49f-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="0a49f-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)