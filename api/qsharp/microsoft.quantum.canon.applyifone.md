---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841768"
---
# <a name="applyifone-operation"></a><span data-ttu-id="c98a4-102">ApplyIfOne-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c98a4-102">ApplyIfOne operation</span></span>

<span data-ttu-id="c98a4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c98a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c98a4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c98a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c98a4-105">Tillämpar en åtgärd i ett klassiskt resultat värde som en.</span><span class="sxs-lookup"><span data-stu-id="c98a4-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="c98a4-106">Description</span><span class="sxs-lookup"><span data-stu-id="c98a4-106">Description</span></span>

<span data-ttu-id="c98a4-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="c98a4-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="c98a4-108">Om `Zero` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="c98a4-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="c98a4-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c98a4-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c98a4-110">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="c98a4-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="c98a4-111">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="c98a4-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="c98a4-112">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c98a4-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c98a4-113">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="c98a4-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="c98a4-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="c98a4-114">target : 'T</span></span>

<span data-ttu-id="c98a4-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="c98a4-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c98a4-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c98a4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c98a4-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c98a4-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c98a4-118">Inte</span><span class="sxs-lookup"><span data-stu-id="c98a4-118">'T</span></span>

<span data-ttu-id="c98a4-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="c98a4-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c98a4-120">Se även</span><span class="sxs-lookup"><span data-stu-id="c98a4-120">See Also</span></span>

- [<span data-ttu-id="c98a4-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="c98a4-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="c98a4-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="c98a4-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="c98a4-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="c98a4-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)