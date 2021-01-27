---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850834"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="65c83-102">ApplyToEachIndexA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="65c83-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="65c83-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65c83-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65c83-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65c83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65c83-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="65c83-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="65c83-106">Modifieraren `A` anger att en qubit-åtgärd är adjointable.</span><span class="sxs-lookup"><span data-stu-id="65c83-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="65c83-107">Indata</span><span class="sxs-lookup"><span data-stu-id="65c83-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="65c83-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="65c83-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="65c83-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="65c83-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="65c83-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="65c83-110">register : 'T[]</span></span>

<span data-ttu-id="65c83-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="65c83-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65c83-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65c83-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65c83-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="65c83-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65c83-114">Inte</span><span class="sxs-lookup"><span data-stu-id="65c83-114">'T</span></span>

<span data-ttu-id="65c83-115">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="65c83-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="65c83-116">Se även</span><span class="sxs-lookup"><span data-stu-id="65c83-116">See Also</span></span>

- [<span data-ttu-id="65c83-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="65c83-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)