---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209426"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="c4247-102">ApplyIfOneC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c4247-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="c4247-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4247-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4247-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4247-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4247-105">Använder en åtgärd som kan kontrol leras på ett klassiskt resultat värde som en.</span><span class="sxs-lookup"><span data-stu-id="c4247-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="c4247-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4247-106">Description</span></span>

<span data-ttu-id="c4247-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="c4247-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="c4247-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="c4247-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="c4247-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="c4247-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="c4247-110">Indata</span><span class="sxs-lookup"><span data-stu-id="c4247-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c4247-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="c4247-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="c4247-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="c4247-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c4247-113">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="c4247-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c4247-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="c4247-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="c4247-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="c4247-115">target : 'T</span></span>

<span data-ttu-id="c4247-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="c4247-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4247-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4247-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4247-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c4247-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4247-119">Inte</span><span class="sxs-lookup"><span data-stu-id="c4247-119">'T</span></span>

<span data-ttu-id="c4247-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="c4247-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4247-121">Se även</span><span class="sxs-lookup"><span data-stu-id="c4247-121">See Also</span></span>

- [<span data-ttu-id="c4247-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="c4247-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="c4247-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="c4247-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="c4247-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="c4247-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)