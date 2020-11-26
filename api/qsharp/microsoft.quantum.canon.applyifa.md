---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218775"
---
# <a name="applyifa-operation"></a><span data-ttu-id="35373-102">ApplyIfA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="35373-102">ApplyIfA operation</span></span>

<span data-ttu-id="35373-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35373-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35373-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35373-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35373-105">Tillämpar en adjointable-åtgärd som villkorat på en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="35373-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="35373-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="35373-106">Description</span></span>

<span data-ttu-id="35373-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="35373-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="35373-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="35373-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="35373-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="35373-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="35373-110">Indata</span><span class="sxs-lookup"><span data-stu-id="35373-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="35373-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="35373-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="35373-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="35373-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="35373-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35373-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35373-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="35373-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="35373-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="35373-115">target : 'T</span></span>

<span data-ttu-id="35373-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="35373-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35373-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35373-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35373-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="35373-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35373-119">Inte</span><span class="sxs-lookup"><span data-stu-id="35373-119">'T</span></span>

<span data-ttu-id="35373-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="35373-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="35373-121">Se även</span><span class="sxs-lookup"><span data-stu-id="35373-121">See Also</span></span>

- [<span data-ttu-id="35373-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="35373-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="35373-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="35373-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="35373-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="35373-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)