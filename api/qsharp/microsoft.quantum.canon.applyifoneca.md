---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729514"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="f7fe6-102">ApplyIfOneCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f7fe6-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="f7fe6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7fe6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7fe6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7fe6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7fe6-105">Använder en åtgärd med ett enhetligt värde som är ett klassiskt resultat värde.</span><span class="sxs-lookup"><span data-stu-id="f7fe6-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="f7fe6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f7fe6-106">Description</span></span>

<span data-ttu-id="f7fe6-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="f7fe6-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f7fe6-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="f7fe6-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f7fe6-109">Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).</span><span class="sxs-lookup"><span data-stu-id="f7fe6-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="f7fe6-110">Indata</span><span class="sxs-lookup"><span data-stu-id="f7fe6-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f7fe6-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="f7fe6-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f7fe6-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="f7fe6-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="f7fe6-113">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="f7fe6-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f7fe6-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f7fe6-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f7fe6-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="f7fe6-115">target : 'T</span></span>

<span data-ttu-id="f7fe6-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="f7fe6-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7fe6-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7fe6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7fe6-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f7fe6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7fe6-119">Inte</span><span class="sxs-lookup"><span data-stu-id="f7fe6-119">'T</span></span>

<span data-ttu-id="f7fe6-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f7fe6-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7fe6-121">Se även</span><span class="sxs-lookup"><span data-stu-id="f7fe6-121">See Also</span></span>

- [<span data-ttu-id="f7fe6-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f7fe6-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f7fe6-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f7fe6-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f7fe6-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f7fe6-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)