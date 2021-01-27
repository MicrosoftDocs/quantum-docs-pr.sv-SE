---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844630"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="910a4-102">ApplyToEach-åtgärd</span><span class="sxs-lookup"><span data-stu-id="910a4-102">ApplyToEach operation</span></span>

<span data-ttu-id="910a4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="910a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="910a4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="910a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="910a4-105">Tillämpar en enskild qubit-åtgärd för varje-element i en register.</span><span class="sxs-lookup"><span data-stu-id="910a4-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="910a4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="910a4-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="910a4-107">singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="910a4-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="910a4-108">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="910a4-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="910a4-109">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="910a4-109">register : 'T[]</span></span>

<span data-ttu-id="910a4-110">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="910a4-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="910a4-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="910a4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="910a4-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="910a4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="910a4-113">Inte</span><span class="sxs-lookup"><span data-stu-id="910a4-113">'T</span></span>

<span data-ttu-id="910a4-114">Målet som åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="910a4-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="910a4-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="910a4-115">Example</span></span>

<span data-ttu-id="910a4-116">Förbered ett tre-qubit $ \ket{+} $-tillstånd:</span><span class="sxs-lookup"><span data-stu-id="910a4-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="910a4-117">Se även</span><span class="sxs-lookup"><span data-stu-id="910a4-117">See Also</span></span>

- [<span data-ttu-id="910a4-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="910a4-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="910a4-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="910a4-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="910a4-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="910a4-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)