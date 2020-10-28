---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729310"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="20be7-102">ApplyToEach-åtgärd</span><span class="sxs-lookup"><span data-stu-id="20be7-102">ApplyToEach operation</span></span>

<span data-ttu-id="20be7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20be7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20be7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20be7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20be7-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="20be7-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="20be7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="20be7-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="20be7-107">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20be7-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20be7-108">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="20be7-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="20be7-109">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="20be7-109">register : 'T[]</span></span>

<span data-ttu-id="20be7-110">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="20be7-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20be7-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20be7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="20be7-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="20be7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20be7-113">Inte</span><span class="sxs-lookup"><span data-stu-id="20be7-113">'T</span></span>

<span data-ttu-id="20be7-114">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="20be7-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="20be7-115">Se även</span><span class="sxs-lookup"><span data-stu-id="20be7-115">See Also</span></span>

- [<span data-ttu-id="20be7-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="20be7-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="20be7-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="20be7-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="20be7-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="20be7-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)