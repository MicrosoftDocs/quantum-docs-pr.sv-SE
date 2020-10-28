---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729579"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="729b6-102">ApplyIfElseBC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="729b6-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="729b6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="729b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="729b6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="729b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="729b6-105">Använder en av två kontrollerbara åtgärder, beroende på värdet för en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="729b6-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="729b6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="729b6-106">Description</span></span>

<span data-ttu-id="729b6-107">Med en bit `bit` , använder åtgärden `trueOp` med `trueInput` som indatatyp när `bit` är `true` , och gäller `falseOp(falseInput)` när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="729b6-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="729b6-108">Indata</span><span class="sxs-lookup"><span data-stu-id="729b6-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="729b6-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="729b6-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="729b6-110">Det booleska värde som används för att avgöra om `trueOp` eller `falseOp` används.</span><span class="sxs-lookup"><span data-stu-id="729b6-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-ctl"></a><span data-ttu-id="729b6-111">trueOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="729b6-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="729b6-112">Den kontrollerbara åtgärd som ska tillämpas när `bit` är `true` .</span><span class="sxs-lookup"><span data-stu-id="729b6-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="729b6-113">trueInput: ' t</span><span class="sxs-lookup"><span data-stu-id="729b6-113">trueInput : 'T</span></span>

<span data-ttu-id="729b6-114">Indata som ska anges till `trueOp` när `bit` är `true` .</span><span class="sxs-lookup"><span data-stu-id="729b6-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-ctl"></a><span data-ttu-id="729b6-115">falseOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="729b6-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="729b6-116">Den kontrollerbara åtgärd som ska tillämpas när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="729b6-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="729b6-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="729b6-117">falseInput : 'U</span></span>

<span data-ttu-id="729b6-118">Indata som ska anges till `falseOp` när `bit` är `false` .</span><span class="sxs-lookup"><span data-stu-id="729b6-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="729b6-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="729b6-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="729b6-120">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="729b6-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="729b6-121">Inte</span><span class="sxs-lookup"><span data-stu-id="729b6-121">'T</span></span>

<span data-ttu-id="729b6-122">Indatatypen för den åtgärd `trueOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="729b6-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="729b6-123">' U</span><span class="sxs-lookup"><span data-stu-id="729b6-123">'U</span></span>

<span data-ttu-id="729b6-124">Indatatypen för den åtgärd `falseOp` som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="729b6-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="729b6-125">Se även</span><span class="sxs-lookup"><span data-stu-id="729b6-125">See Also</span></span>

- [<span data-ttu-id="729b6-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="729b6-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="729b6-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="729b6-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="729b6-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="729b6-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="729b6-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="729b6-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="729b6-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="729b6-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)