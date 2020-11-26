---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209629"
---
# <a name="applyifca-operation"></a><span data-ttu-id="904c6-102">ApplyIfCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="904c6-102">ApplyIfCA operation</span></span>

<span data-ttu-id="904c6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="904c6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="904c6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="904c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="904c6-105">Använder en enhetlig åtgärd som är villkorlig för en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="904c6-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="904c6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="904c6-106">Description</span></span>

<span data-ttu-id="904c6-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="904c6-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="904c6-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="904c6-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="904c6-109">Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).</span><span class="sxs-lookup"><span data-stu-id="904c6-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="904c6-110">Indata</span><span class="sxs-lookup"><span data-stu-id="904c6-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="904c6-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="904c6-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="904c6-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="904c6-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="904c6-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="904c6-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="904c6-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="904c6-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="904c6-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="904c6-115">target : 'T</span></span>

<span data-ttu-id="904c6-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="904c6-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="904c6-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="904c6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="904c6-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="904c6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="904c6-119">Inte</span><span class="sxs-lookup"><span data-stu-id="904c6-119">'T</span></span>

<span data-ttu-id="904c6-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="904c6-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="904c6-121">Se även</span><span class="sxs-lookup"><span data-stu-id="904c6-121">See Also</span></span>

- [<span data-ttu-id="904c6-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="904c6-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="904c6-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="904c6-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="904c6-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="904c6-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)