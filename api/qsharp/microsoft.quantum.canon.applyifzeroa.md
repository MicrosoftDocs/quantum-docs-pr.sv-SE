---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: ApplyIfZeroA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729508"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="464be-102">ApplyIfZeroA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="464be-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="464be-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="464be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="464be-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="464be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="464be-105">Tillämpar en adjointable-åtgärd med villkoret på ett klassiskt resultat värde som noll.</span><span class="sxs-lookup"><span data-stu-id="464be-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="464be-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="464be-106">Description</span></span>

<span data-ttu-id="464be-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="464be-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="464be-108">Om `One` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="464be-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="464be-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="464be-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="464be-110">Indata</span><span class="sxs-lookup"><span data-stu-id="464be-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="464be-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="464be-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="464be-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="464be-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="464be-113">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="464be-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="464be-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="464be-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="464be-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="464be-115">target : 'T</span></span>

<span data-ttu-id="464be-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="464be-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="464be-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="464be-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="464be-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="464be-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="464be-119">Inte</span><span class="sxs-lookup"><span data-stu-id="464be-119">'T</span></span>

<span data-ttu-id="464be-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="464be-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="464be-121">Se även</span><span class="sxs-lookup"><span data-stu-id="464be-121">See Also</span></span>

- [<span data-ttu-id="464be-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="464be-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="464be-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="464be-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="464be-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="464be-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)