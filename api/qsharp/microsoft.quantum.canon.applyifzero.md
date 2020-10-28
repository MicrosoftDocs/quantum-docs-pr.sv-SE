---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729511"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="7d475-102">ApplyIfZero-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7d475-102">ApplyIfZero operation</span></span>

<span data-ttu-id="7d475-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d475-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d475-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d475-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d475-105">Tillämpar ett åtgärds villkor på ett klassiskt resultat värde som noll.</span><span class="sxs-lookup"><span data-stu-id="7d475-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="7d475-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7d475-106">Description</span></span>

<span data-ttu-id="7d475-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7d475-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="7d475-108">Om `One` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="7d475-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="7d475-109">Indata</span><span class="sxs-lookup"><span data-stu-id="7d475-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7d475-110">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="7d475-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="7d475-111">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="7d475-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="7d475-112">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d475-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7d475-113">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="7d475-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7d475-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="7d475-114">target : 'T</span></span>

<span data-ttu-id="7d475-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="7d475-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d475-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d475-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d475-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7d475-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d475-118">Inte</span><span class="sxs-lookup"><span data-stu-id="7d475-118">'T</span></span>

<span data-ttu-id="7d475-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="7d475-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d475-120">Se även</span><span class="sxs-lookup"><span data-stu-id="7d475-120">See Also</span></span>

- [<span data-ttu-id="7d475-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="7d475-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="7d475-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="7d475-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="7d475-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="7d475-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)