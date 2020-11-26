---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218588"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="f4589-102">ApplyIfOneCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f4589-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="f4589-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4589-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4589-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4589-105">Använder en åtgärd med ett enhetligt värde som är ett klassiskt resultat värde.</span><span class="sxs-lookup"><span data-stu-id="f4589-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f4589-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f4589-106">Description</span></span>

<span data-ttu-id="f4589-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="f4589-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f4589-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="f4589-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f4589-109">Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).</span><span class="sxs-lookup"><span data-stu-id="f4589-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="f4589-110">Indata</span><span class="sxs-lookup"><span data-stu-id="f4589-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f4589-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="f4589-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f4589-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="f4589-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="f4589-113">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="f4589-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f4589-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f4589-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f4589-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="f4589-115">target : 'T</span></span>

<span data-ttu-id="f4589-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="f4589-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4589-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4589-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4589-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f4589-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4589-119">Inte</span><span class="sxs-lookup"><span data-stu-id="f4589-119">'T</span></span>

<span data-ttu-id="f4589-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f4589-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4589-121">Se även</span><span class="sxs-lookup"><span data-stu-id="f4589-121">See Also</span></span>

- [<span data-ttu-id="f4589-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f4589-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f4589-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f4589-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f4589-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f4589-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)