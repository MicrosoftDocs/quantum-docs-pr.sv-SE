---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729526"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="3c06f-102">ApplyIfOneA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3c06f-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="3c06f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c06f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c06f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c06f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c06f-105">Tillämpar en adjointable-åtgärd som har ett klassiskt resultat värde som ett.</span><span class="sxs-lookup"><span data-stu-id="3c06f-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="3c06f-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3c06f-106">Description</span></span>

<span data-ttu-id="3c06f-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="3c06f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="3c06f-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="3c06f-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3c06f-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="3c06f-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="3c06f-110">Indata</span><span class="sxs-lookup"><span data-stu-id="3c06f-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3c06f-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="3c06f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3c06f-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="3c06f-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="3c06f-113">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="3c06f-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3c06f-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="3c06f-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3c06f-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="3c06f-115">target : 'T</span></span>

<span data-ttu-id="3c06f-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="3c06f-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c06f-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c06f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c06f-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3c06f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c06f-119">Inte</span><span class="sxs-lookup"><span data-stu-id="3c06f-119">'T</span></span>

<span data-ttu-id="3c06f-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="3c06f-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c06f-121">Se även</span><span class="sxs-lookup"><span data-stu-id="3c06f-121">See Also</span></span>

- [<span data-ttu-id="3c06f-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3c06f-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="3c06f-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="3c06f-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="3c06f-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="3c06f-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)