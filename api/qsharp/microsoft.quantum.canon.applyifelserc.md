---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209493"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="31e0a-102">ApplyIfElseRC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="31e0a-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="31e0a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="31e0a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="31e0a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31e0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31e0a-105">Använder en av två kontrollerbara åtgärder, beroende på värdet för ett klassiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="31e0a-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="31e0a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="31e0a-106">Description</span></span>

<span data-ttu-id="31e0a-107">`result`På grund av detta tillämpas åtgärden `zeroOp` med `zeroInput` som indatamängden när `result` är lika med `Zero` , och tillämpas `oneOp(oneInput)` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="31e0a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="31e0a-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="31e0a-109">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="31e0a-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="31e0a-110">Mät resultatet som används för att avgöra om `zeroOp` eller används `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="31e0a-111">zeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="31e0a-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="31e0a-112">Den kontrollerbara åtgärd som ska tillämpas när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="31e0a-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="31e0a-113">zeroInput : 'T</span></span>

<span data-ttu-id="31e0a-114">Indata som ska anges till `zeroOp` när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="31e0a-115">oneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="31e0a-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="31e0a-116">Den kontrollerbara åtgärd som ska tillämpas när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="31e0a-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="31e0a-117">oneInput : 'U</span></span>

<span data-ttu-id="31e0a-118">Indata som ska anges till `oneOp` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="31e0a-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31e0a-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31e0a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="31e0a-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="31e0a-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31e0a-121">Inte</span><span class="sxs-lookup"><span data-stu-id="31e0a-121">'T</span></span>

<span data-ttu-id="31e0a-122">Indatatypen för den åtgärd `zeroOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="31e0a-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="31e0a-123">' U</span><span class="sxs-lookup"><span data-stu-id="31e0a-123">'U</span></span>

<span data-ttu-id="31e0a-124">Indatatypen för den åtgärd `oneOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="31e0a-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="31e0a-125">Se även</span><span class="sxs-lookup"><span data-stu-id="31e0a-125">See Also</span></span>

- [<span data-ttu-id="31e0a-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="31e0a-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="31e0a-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="31e0a-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="31e0a-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="31e0a-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="31e0a-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="31e0a-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="31e0a-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="31e0a-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)