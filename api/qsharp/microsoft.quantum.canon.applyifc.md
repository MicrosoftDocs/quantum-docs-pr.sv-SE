---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218724"
---
# <a name="applyifc-operation"></a><span data-ttu-id="73640-102">ApplyIfC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="73640-102">ApplyIfC operation</span></span>

<span data-ttu-id="73640-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73640-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73640-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73640-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73640-105">Använder en åtgärd som går att kontrol lera i en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="73640-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="73640-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="73640-106">Description</span></span>

<span data-ttu-id="73640-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="73640-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="73640-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="73640-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="73640-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="73640-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="73640-110">Indata</span><span class="sxs-lookup"><span data-stu-id="73640-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="73640-111">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="73640-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="73640-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="73640-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="73640-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="73640-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="73640-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="73640-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="73640-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="73640-115">target : 'T</span></span>

<span data-ttu-id="73640-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="73640-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73640-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73640-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="73640-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="73640-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="73640-119">Inte</span><span class="sxs-lookup"><span data-stu-id="73640-119">'T</span></span>

<span data-ttu-id="73640-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="73640-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="73640-121">Se även</span><span class="sxs-lookup"><span data-stu-id="73640-121">See Also</span></span>

- [<span data-ttu-id="73640-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="73640-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="73640-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="73640-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="73640-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="73640-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)