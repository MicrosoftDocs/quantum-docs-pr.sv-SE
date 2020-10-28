---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 9a2e020c596b02d9cb38309d02ca02056c1dec75
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729523"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="93cc5-102">ApplyIfOneC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="93cc5-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="93cc5-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93cc5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93cc5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93cc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93cc5-105">Använder en åtgärd som kan kontrol leras på ett klassiskt resultat värde som en.</span><span class="sxs-lookup"><span data-stu-id="93cc5-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="93cc5-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="93cc5-106">Description</span></span>

<span data-ttu-id="93cc5-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="93cc5-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="93cc5-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="93cc5-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="93cc5-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="93cc5-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="93cc5-110">Indata</span><span class="sxs-lookup"><span data-stu-id="93cc5-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="93cc5-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="93cc5-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="93cc5-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="93cc5-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="93cc5-113">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="93cc5-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="93cc5-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="93cc5-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="93cc5-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="93cc5-115">target : 'T</span></span>

<span data-ttu-id="93cc5-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="93cc5-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93cc5-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93cc5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93cc5-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="93cc5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93cc5-119">Inte</span><span class="sxs-lookup"><span data-stu-id="93cc5-119">'T</span></span>

<span data-ttu-id="93cc5-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="93cc5-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="93cc5-121">Se även</span><span class="sxs-lookup"><span data-stu-id="93cc5-121">See Also</span></span>

- [<span data-ttu-id="93cc5-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="93cc5-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="93cc5-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="93cc5-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="93cc5-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="93cc5-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)