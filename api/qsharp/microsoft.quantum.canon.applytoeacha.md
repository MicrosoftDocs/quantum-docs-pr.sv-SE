---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844603"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="c042d-102">ApplyToEachA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c042d-102">ApplyToEachA operation</span></span>

<span data-ttu-id="c042d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c042d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c042d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c042d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c042d-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="c042d-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="c042d-106">Modifieraren `A` anger att en qubit-åtgärd är adjointable.</span><span class="sxs-lookup"><span data-stu-id="c042d-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c042d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="c042d-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="c042d-108">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="c042d-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c042d-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="c042d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c042d-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="c042d-110">register : 'T[]</span></span>

<span data-ttu-id="c042d-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="c042d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c042d-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c042d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c042d-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c042d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c042d-114">Inte</span><span class="sxs-lookup"><span data-stu-id="c042d-114">'T</span></span>

<span data-ttu-id="c042d-115">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="c042d-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="c042d-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="c042d-116">Example</span></span>

<span data-ttu-id="c042d-117">Förbered ett tre-qubit $ \ket{+} $-tillstånd:</span><span class="sxs-lookup"><span data-stu-id="c042d-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="c042d-118">Se även</span><span class="sxs-lookup"><span data-stu-id="c042d-118">See Also</span></span>

- [<span data-ttu-id="c042d-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="c042d-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)