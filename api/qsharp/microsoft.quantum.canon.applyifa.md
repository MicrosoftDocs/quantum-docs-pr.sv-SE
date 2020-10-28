---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729603"
---
# <a name="applyifa-operation"></a><span data-ttu-id="ff1e7-102">ApplyIfA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ff1e7-102">ApplyIfA operation</span></span>

<span data-ttu-id="ff1e7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff1e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff1e7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff1e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff1e7-105">Tillämpar en adjointable-åtgärd som villkorat på en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="ff1e7-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff1e7-106">Description</span></span>

<span data-ttu-id="ff1e7-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="ff1e7-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="ff1e7-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="ff1e7-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="ff1e7-109">Suffixet `A` anger att åtgärden som ska tillämpas är adjointable.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="ff1e7-110">Indata</span><span class="sxs-lookup"><span data-stu-id="ff1e7-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="ff1e7-111">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="ff1e7-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ff1e7-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="ff1e7-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff1e7-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff1e7-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="ff1e7-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="ff1e7-115">target : 'T</span></span>

<span data-ttu-id="ff1e7-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff1e7-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff1e7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff1e7-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ff1e7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff1e7-119">Inte</span><span class="sxs-lookup"><span data-stu-id="ff1e7-119">'T</span></span>

<span data-ttu-id="ff1e7-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ff1e7-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff1e7-121">Se även</span><span class="sxs-lookup"><span data-stu-id="ff1e7-121">See Also</span></span>

- [<span data-ttu-id="ff1e7-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="ff1e7-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="ff1e7-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="ff1e7-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="ff1e7-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="ff1e7-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)