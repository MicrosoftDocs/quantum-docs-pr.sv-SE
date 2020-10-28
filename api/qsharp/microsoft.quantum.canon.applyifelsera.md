---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729547"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="983f4-102">ApplyIfElseRA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="983f4-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="983f4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="983f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="983f4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="983f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="983f4-105">Tillämpar en av två adjointable-åtgärder, beroende på värdet för ett klassiskt resultat.</span><span class="sxs-lookup"><span data-stu-id="983f4-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="983f4-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="983f4-106">Description</span></span>

<span data-ttu-id="983f4-107">`result`På grund av detta tillämpas åtgärden `zeroOp` med `zeroInput` som indatamängden när `result` är lika med `Zero` , och tillämpas `oneOp(oneInput)` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="983f4-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="983f4-108">Indata</span><span class="sxs-lookup"><span data-stu-id="983f4-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="983f4-109">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="983f4-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="983f4-110">Mät resultatet som används för att avgöra om `zeroOp` eller används `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="983f4-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj"></a><span data-ttu-id="983f4-111">zeroOp: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="983f4-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="983f4-112">Den adjointable-åtgärd som ska tillämpas när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="983f4-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="983f4-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="983f4-113">zeroInput : 'T</span></span>

<span data-ttu-id="983f4-114">Indata som ska anges till `zeroOp` när `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="983f4-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj"></a><span data-ttu-id="983f4-115">oneOp: ' U => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="983f4-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="983f4-116">Den adjointable-åtgärd som ska tillämpas när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="983f4-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="983f4-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="983f4-117">oneInput : 'U</span></span>

<span data-ttu-id="983f4-118">Indata som ska anges till `oneOp` när `result == One` .</span><span class="sxs-lookup"><span data-stu-id="983f4-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="983f4-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="983f4-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="983f4-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="983f4-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="983f4-121">Inte</span><span class="sxs-lookup"><span data-stu-id="983f4-121">'T</span></span>

<span data-ttu-id="983f4-122">Indatatypen för den åtgärd `zeroOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="983f4-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="983f4-123">' U</span><span class="sxs-lookup"><span data-stu-id="983f4-123">'U</span></span>

<span data-ttu-id="983f4-124">Indatatypen för den åtgärd `oneOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="983f4-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="983f4-125">Se även</span><span class="sxs-lookup"><span data-stu-id="983f4-125">See Also</span></span>

- [<span data-ttu-id="983f4-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="983f4-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="983f4-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="983f4-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="983f4-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="983f4-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="983f4-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="983f4-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="983f4-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="983f4-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)