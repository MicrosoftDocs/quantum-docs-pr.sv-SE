---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729289"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="16474-102">ApplyToEachIndex-åtgärd</span><span class="sxs-lookup"><span data-stu-id="16474-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="16474-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16474-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16474-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16474-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16474-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="16474-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="16474-106">Indata</span><span class="sxs-lookup"><span data-stu-id="16474-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="16474-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16474-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="16474-108">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="16474-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="16474-109">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="16474-109">register : 'T[]</span></span>

<span data-ttu-id="16474-110">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="16474-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16474-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16474-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="16474-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="16474-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16474-113">Inte</span><span class="sxs-lookup"><span data-stu-id="16474-113">'T</span></span>

<span data-ttu-id="16474-114">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="16474-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="16474-115">Se även</span><span class="sxs-lookup"><span data-stu-id="16474-115">See Also</span></span>

- [<span data-ttu-id="16474-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="16474-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="16474-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="16474-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="16474-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="16474-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="16474-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="16474-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)