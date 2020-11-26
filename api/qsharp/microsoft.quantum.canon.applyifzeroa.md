---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: ApplyIfZeroA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218503"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="39490-102">ApplyIfZeroA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="39490-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="39490-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39490-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39490-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39490-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39490-105">Tillämpar en adjointable-åtgärd med villkoret på ett klassiskt resultat värde som noll.</span><span class="sxs-lookup"><span data-stu-id="39490-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="39490-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="39490-106">Description</span></span>

<span data-ttu-id="39490-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="39490-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="39490-108">Om `One` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="39490-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="39490-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="39490-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="39490-110">Indata</span><span class="sxs-lookup"><span data-stu-id="39490-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="39490-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="39490-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="39490-112">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="39490-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="39490-113">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="39490-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39490-114">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="39490-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="39490-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="39490-115">target : 'T</span></span>

<span data-ttu-id="39490-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="39490-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39490-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39490-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39490-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="39490-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39490-119">Inte</span><span class="sxs-lookup"><span data-stu-id="39490-119">'T</span></span>

<span data-ttu-id="39490-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="39490-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="39490-121">Se även</span><span class="sxs-lookup"><span data-stu-id="39490-121">See Also</span></span>

- [<span data-ttu-id="39490-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="39490-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="39490-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="39490-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="39490-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="39490-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)