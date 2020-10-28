---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: c48d75323f036ebce1a316382a05cd2578db47a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729532"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="57a93-102">ApplyIfElseRCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="57a93-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="57a93-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57a93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57a93-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57a93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57a93-105">Använder en av två enhetliga åtgärder, beroende på värdet av ett klassiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="57a93-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="57a93-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="57a93-106">Description</span></span>

<span data-ttu-id="57a93-107">`result`På grund av detta tillämpas åtgärden `zeroOp` med `zeroInput` som indatamängden när `result` är lika med `Zero` , och tillämpas `oneOp(oneInput)` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="57a93-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="57a93-108">Indata</span><span class="sxs-lookup"><span data-stu-id="57a93-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="57a93-109">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="57a93-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="57a93-110">Mät resultatet som används för att avgöra om `zeroOp` eller används `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="57a93-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj--ctl"></a><span data-ttu-id="57a93-111">zeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="57a93-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="57a93-112">Den enhetliga åtgärd som ska tillämpas när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="57a93-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="57a93-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="57a93-113">zeroInput : 'T</span></span>

<span data-ttu-id="57a93-114">Indata som ska anges till `zeroOp` när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="57a93-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj--ctl"></a><span data-ttu-id="57a93-115">oneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="57a93-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="57a93-116">Den enhetliga åtgärd som ska tillämpas när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="57a93-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="57a93-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="57a93-117">oneInput : 'U</span></span>

<span data-ttu-id="57a93-118">Indata som ska anges till `oneOp` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="57a93-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57a93-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57a93-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57a93-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="57a93-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57a93-121">Inte</span><span class="sxs-lookup"><span data-stu-id="57a93-121">'T</span></span>

<span data-ttu-id="57a93-122">Indatatypen för den åtgärd `zeroOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="57a93-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="57a93-123">' U</span><span class="sxs-lookup"><span data-stu-id="57a93-123">'U</span></span>

<span data-ttu-id="57a93-124">Indatatypen för den åtgärd `oneOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="57a93-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="57a93-125">Se även</span><span class="sxs-lookup"><span data-stu-id="57a93-125">See Also</span></span>

- [<span data-ttu-id="57a93-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="57a93-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="57a93-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="57a93-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="57a93-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="57a93-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="57a93-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="57a93-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="57a93-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="57a93-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)