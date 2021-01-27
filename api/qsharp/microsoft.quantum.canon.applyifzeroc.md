---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841725"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="50bc8-102">ApplyIfZeroC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="50bc8-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="50bc8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50bc8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50bc8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50bc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50bc8-105">Använder en åtgärd som kan kontrol leras på ett klassiskt resultat värde som noll.</span><span class="sxs-lookup"><span data-stu-id="50bc8-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="50bc8-106">Description</span><span class="sxs-lookup"><span data-stu-id="50bc8-106">Description</span></span>

<span data-ttu-id="50bc8-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="50bc8-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="50bc8-108">Om `One` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="50bc8-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="50bc8-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="50bc8-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="50bc8-110">Indata</span><span class="sxs-lookup"><span data-stu-id="50bc8-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="50bc8-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="50bc8-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="50bc8-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="50bc8-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="50bc8-113">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="50bc8-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="50bc8-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="50bc8-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="50bc8-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="50bc8-115">target : 'T</span></span>

<span data-ttu-id="50bc8-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="50bc8-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50bc8-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50bc8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50bc8-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="50bc8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50bc8-119">Inte</span><span class="sxs-lookup"><span data-stu-id="50bc8-119">'T</span></span>

<span data-ttu-id="50bc8-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="50bc8-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="50bc8-121">Se även</span><span class="sxs-lookup"><span data-stu-id="50bc8-121">See Also</span></span>

- [<span data-ttu-id="50bc8-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="50bc8-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="50bc8-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="50bc8-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="50bc8-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="50bc8-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)