---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: ea06b0a0a07659407e13caa2baa4f3e37ca2a0f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209527"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="4cbcc-102">ApplyIfElseBC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4cbcc-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="4cbcc-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4cbcc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4cbcc-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cbcc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cbcc-105">Använder en av två kontrollerbara åtgärder, beroende på värdet för en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="4cbcc-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="4cbcc-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4cbcc-106">Description</span></span>

<span data-ttu-id="4cbcc-107">Med en bit `bit` , använder åtgärden `trueOp` med `trueInput` som indatatyp när `bit` är `true` , och gäller `falseOp(falseInput)` när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="4cbcc-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="4cbcc-108">Indata</span><span class="sxs-lookup"><span data-stu-id="4cbcc-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="4cbcc-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4cbcc-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4cbcc-110">Det booleska värde som används för att avgöra om `trueOp` eller `falseOp` används.</span><span class="sxs-lookup"><span data-stu-id="4cbcc-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-ctl"></a><span data-ttu-id="4cbcc-111">trueOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="4cbcc-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4cbcc-112">Den kontrollerbara åtgärd som ska tillämpas när `bit` är `true` .</span><span class="sxs-lookup"><span data-stu-id="4cbcc-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="4cbcc-113">trueInput: ' t</span><span class="sxs-lookup"><span data-stu-id="4cbcc-113">trueInput : 'T</span></span>

<span data-ttu-id="4cbcc-114">Indata som ska anges till `trueOp` när `bit` är `true` .</span><span class="sxs-lookup"><span data-stu-id="4cbcc-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-ctl"></a><span data-ttu-id="4cbcc-115">falseOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="4cbcc-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4cbcc-116">Den kontrollerbara åtgärd som ska tillämpas när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="4cbcc-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="4cbcc-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="4cbcc-117">falseInput : 'U</span></span>

<span data-ttu-id="4cbcc-118">Indata som ska anges till `falseOp` när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="4cbcc-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cbcc-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cbcc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4cbcc-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4cbcc-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4cbcc-121">Inte</span><span class="sxs-lookup"><span data-stu-id="4cbcc-121">'T</span></span>

<span data-ttu-id="4cbcc-122">Indatatypen för den åtgärd `trueOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="4cbcc-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="4cbcc-123">' U</span><span class="sxs-lookup"><span data-stu-id="4cbcc-123">'U</span></span>

<span data-ttu-id="4cbcc-124">Indatatypen för den åtgärd `falseOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="4cbcc-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cbcc-125">Se även</span><span class="sxs-lookup"><span data-stu-id="4cbcc-125">See Also</span></span>

- [<span data-ttu-id="4cbcc-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="4cbcc-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="4cbcc-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="4cbcc-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="4cbcc-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="4cbcc-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="4cbcc-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="4cbcc-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="4cbcc-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="4cbcc-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)