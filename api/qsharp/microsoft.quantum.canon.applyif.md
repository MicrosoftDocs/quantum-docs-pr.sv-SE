---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218843"
---
# <a name="applyif-operation"></a><span data-ttu-id="3c582-102">ApplyIf-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3c582-102">ApplyIf operation</span></span>

<span data-ttu-id="3c582-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c582-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c582-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c582-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c582-105">Tillämpar en åtgärd som villkoras på en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="3c582-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="3c582-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3c582-106">Description</span></span>

<span data-ttu-id="3c582-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="3c582-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="3c582-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="3c582-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="3c582-109">Indata</span><span class="sxs-lookup"><span data-stu-id="3c582-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="3c582-110">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c582-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3c582-111">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="3c582-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="3c582-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3c582-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3c582-113">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="3c582-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="3c582-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="3c582-114">target : 'T</span></span>

<span data-ttu-id="3c582-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="3c582-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c582-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c582-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c582-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3c582-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c582-118">Inte</span><span class="sxs-lookup"><span data-stu-id="3c582-118">'T</span></span>

<span data-ttu-id="3c582-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="3c582-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c582-120">Se även</span><span class="sxs-lookup"><span data-stu-id="3c582-120">See Also</span></span>

- [<span data-ttu-id="3c582-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="3c582-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="3c582-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="3c582-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="3c582-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="3c582-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)