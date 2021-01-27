---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844598"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="55ba7-102">ApplyToEachIndex-åtgärd</span><span class="sxs-lookup"><span data-stu-id="55ba7-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="55ba7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55ba7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55ba7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55ba7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55ba7-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="55ba7-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="55ba7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="55ba7-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="55ba7-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55ba7-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="55ba7-108">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="55ba7-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="55ba7-109">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="55ba7-109">register : 'T[]</span></span>

<span data-ttu-id="55ba7-110">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="55ba7-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55ba7-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55ba7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55ba7-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="55ba7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55ba7-113">Inte</span><span class="sxs-lookup"><span data-stu-id="55ba7-113">'T</span></span>

<span data-ttu-id="55ba7-114">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="55ba7-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="55ba7-115">Se även</span><span class="sxs-lookup"><span data-stu-id="55ba7-115">See Also</span></span>

- [<span data-ttu-id="55ba7-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="55ba7-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="55ba7-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="55ba7-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="55ba7-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="55ba7-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="55ba7-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="55ba7-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)