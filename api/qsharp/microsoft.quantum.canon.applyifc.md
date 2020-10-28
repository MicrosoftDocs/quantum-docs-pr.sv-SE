---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729595"
---
# <a name="applyifc-operation"></a><span data-ttu-id="e87c7-102">ApplyIfC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e87c7-102">ApplyIfC operation</span></span>

<span data-ttu-id="e87c7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e87c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e87c7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e87c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e87c7-105">Använder en åtgärd som går att kontrol lera i en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="e87c7-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="e87c7-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e87c7-106">Description</span></span>

<span data-ttu-id="e87c7-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="e87c7-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e87c7-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="e87c7-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="e87c7-110">Indata</span><span class="sxs-lookup"><span data-stu-id="e87c7-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="e87c7-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="e87c7-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e87c7-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="e87c7-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e87c7-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e87c7-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="e87c7-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="e87c7-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="e87c7-115">target : 'T</span></span>

<span data-ttu-id="e87c7-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e87c7-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e87c7-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e87c7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e87c7-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e87c7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e87c7-119">Inte</span><span class="sxs-lookup"><span data-stu-id="e87c7-119">'T</span></span>

<span data-ttu-id="e87c7-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e87c7-121">Se även</span><span class="sxs-lookup"><span data-stu-id="e87c7-121">See Also</span></span>

- [<span data-ttu-id="e87c7-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="e87c7-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="e87c7-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="e87c7-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="e87c7-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="e87c7-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)