---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729598"
---
# <a name="applyif-operation"></a><span data-ttu-id="54040-102">ApplyIf-åtgärd</span><span class="sxs-lookup"><span data-stu-id="54040-102">ApplyIf operation</span></span>

<span data-ttu-id="54040-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54040-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54040-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54040-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54040-105">Tillämpar en åtgärd som villkoras på en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="54040-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="54040-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="54040-106">Description</span></span>

<span data-ttu-id="54040-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="54040-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="54040-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="54040-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="54040-109">Indata</span><span class="sxs-lookup"><span data-stu-id="54040-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="54040-110">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54040-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="54040-111">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="54040-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="54040-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54040-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54040-113">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="54040-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="54040-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="54040-114">target : 'T</span></span>

<span data-ttu-id="54040-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="54040-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54040-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54040-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54040-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="54040-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54040-118">Inte</span><span class="sxs-lookup"><span data-stu-id="54040-118">'T</span></span>

<span data-ttu-id="54040-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="54040-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="54040-120">Se även</span><span class="sxs-lookup"><span data-stu-id="54040-120">See Also</span></span>

- [<span data-ttu-id="54040-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="54040-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="54040-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="54040-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="54040-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="54040-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)