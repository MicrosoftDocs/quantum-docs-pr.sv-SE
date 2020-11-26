---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209544"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="60447-102">ApplyIfElseR-åtgärd</span><span class="sxs-lookup"><span data-stu-id="60447-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="60447-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60447-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60447-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60447-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60447-105">Tillämpar en av två åtgärder, beroende på värdet för ett klassiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="60447-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="60447-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="60447-106">Description</span></span>

<span data-ttu-id="60447-107">`result`På grund av detta tillämpas åtgärden `zeroOp` med `zeroInput` som indatamängden när `result` är lika med `Zero` , och tillämpas `oneOp(oneInput)` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="60447-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="60447-108">Indata</span><span class="sxs-lookup"><span data-stu-id="60447-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="60447-109">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="60447-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="60447-110">Mät resultatet som används för att avgöra om `zeroOp` eller används `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="60447-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="60447-111">zeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60447-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="60447-112">Den åtgärd som ska tillämpas när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="60447-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="60447-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="60447-113">zeroInput : 'T</span></span>

<span data-ttu-id="60447-114">Indata som ska anges till `zeroOp` när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="60447-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="60447-115">oneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60447-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="60447-116">Den åtgärd som ska tillämpas när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="60447-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="60447-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="60447-117">oneInput : 'U</span></span>

<span data-ttu-id="60447-118">Indata som ska anges till `oneOp` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="60447-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60447-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60447-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60447-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="60447-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60447-121">Inte</span><span class="sxs-lookup"><span data-stu-id="60447-121">'T</span></span>

<span data-ttu-id="60447-122">Indatatypen för den åtgärd `zeroOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="60447-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="60447-123">' U</span><span class="sxs-lookup"><span data-stu-id="60447-123">'U</span></span>

<span data-ttu-id="60447-124">Indatatypen för den åtgärd `oneOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="60447-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="60447-125">Se även</span><span class="sxs-lookup"><span data-stu-id="60447-125">See Also</span></span>

- [<span data-ttu-id="60447-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="60447-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="60447-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="60447-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="60447-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="60447-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="60447-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="60447-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="60447-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="60447-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)