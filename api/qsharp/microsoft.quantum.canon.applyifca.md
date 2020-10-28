---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729590"
---
# <a name="applyifca-operation"></a><span data-ttu-id="6ec02-102">ApplyIfCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6ec02-102">ApplyIfCA operation</span></span>

<span data-ttu-id="6ec02-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ec02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ec02-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ec02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ec02-105">Använder en enhetlig åtgärd som är villkorlig för en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="6ec02-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="6ec02-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6ec02-106">Description</span></span>

<span data-ttu-id="6ec02-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="6ec02-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="6ec02-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="6ec02-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="6ec02-109">Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).</span><span class="sxs-lookup"><span data-stu-id="6ec02-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="6ec02-110">Indata</span><span class="sxs-lookup"><span data-stu-id="6ec02-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="6ec02-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="6ec02-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="6ec02-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="6ec02-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="6ec02-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ec02-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ec02-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="6ec02-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="6ec02-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="6ec02-115">target : 'T</span></span>

<span data-ttu-id="6ec02-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="6ec02-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ec02-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ec02-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ec02-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6ec02-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ec02-119">Inte</span><span class="sxs-lookup"><span data-stu-id="6ec02-119">'T</span></span>

<span data-ttu-id="6ec02-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="6ec02-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ec02-121">Se även</span><span class="sxs-lookup"><span data-stu-id="6ec02-121">See Also</span></span>

- [<span data-ttu-id="6ec02-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="6ec02-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="6ec02-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="6ec02-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="6ec02-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="6ec02-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)