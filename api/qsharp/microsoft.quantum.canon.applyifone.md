---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729529"
---
# <a name="applyifone-operation"></a><span data-ttu-id="01297-102">ApplyIfOne-åtgärd</span><span class="sxs-lookup"><span data-stu-id="01297-102">ApplyIfOne operation</span></span>

<span data-ttu-id="01297-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01297-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01297-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01297-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01297-105">Tillämpar en åtgärd i ett klassiskt resultat värde som en.</span><span class="sxs-lookup"><span data-stu-id="01297-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="01297-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="01297-106">Description</span></span>

<span data-ttu-id="01297-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="01297-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="01297-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="01297-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="01297-109">Indata</span><span class="sxs-lookup"><span data-stu-id="01297-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="01297-110">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="01297-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="01297-111">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="01297-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="01297-112">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01297-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="01297-113">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="01297-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="01297-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="01297-114">target : 'T</span></span>

<span data-ttu-id="01297-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="01297-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01297-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01297-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="01297-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="01297-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01297-118">Inte</span><span class="sxs-lookup"><span data-stu-id="01297-118">'T</span></span>

<span data-ttu-id="01297-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="01297-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="01297-120">Se även</span><span class="sxs-lookup"><span data-stu-id="01297-120">See Also</span></span>

- [<span data-ttu-id="01297-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="01297-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="01297-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="01297-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="01297-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="01297-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)