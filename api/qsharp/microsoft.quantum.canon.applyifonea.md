---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844934"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="f90da-102">ApplyIfOneA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f90da-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="f90da-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f90da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f90da-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f90da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f90da-105">Tillämpar en adjointable-åtgärd som har ett klassiskt resultat värde som ett.</span><span class="sxs-lookup"><span data-stu-id="f90da-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="f90da-106">Description</span><span class="sxs-lookup"><span data-stu-id="f90da-106">Description</span></span>

<span data-ttu-id="f90da-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="f90da-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f90da-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="f90da-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f90da-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="f90da-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="f90da-110">Indata</span><span class="sxs-lookup"><span data-stu-id="f90da-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f90da-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="f90da-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f90da-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="f90da-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f90da-113">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="f90da-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f90da-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f90da-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f90da-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="f90da-115">target : 'T</span></span>

<span data-ttu-id="f90da-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="f90da-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f90da-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f90da-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f90da-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f90da-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f90da-119">Inte</span><span class="sxs-lookup"><span data-stu-id="f90da-119">'T</span></span>

<span data-ttu-id="f90da-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="f90da-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f90da-121">Se även</span><span class="sxs-lookup"><span data-stu-id="f90da-121">See Also</span></span>

- [<span data-ttu-id="f90da-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f90da-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f90da-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f90da-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f90da-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f90da-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)