---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728752"
---
# <a name="delayc-operation"></a><span data-ttu-id="270b2-102">DelayC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="270b2-102">DelayC operation</span></span>

<span data-ttu-id="270b2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="270b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="270b2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="270b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="270b2-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="270b2-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="270b2-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="270b2-106">Description</span></span>

<span data-ttu-id="270b2-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="270b2-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="270b2-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="270b2-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="270b2-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="270b2-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="270b2-110">Indata</span><span class="sxs-lookup"><span data-stu-id="270b2-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="270b2-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="270b2-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="270b2-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="270b2-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="270b2-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="270b2-113">arg : 'T</span></span>

<span data-ttu-id="270b2-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="270b2-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="270b2-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="270b2-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="270b2-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="270b2-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="270b2-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="270b2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="270b2-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="270b2-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="270b2-119">Inte</span><span class="sxs-lookup"><span data-stu-id="270b2-119">'T</span></span>

<span data-ttu-id="270b2-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="270b2-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="270b2-121">Se även</span><span class="sxs-lookup"><span data-stu-id="270b2-121">See Also</span></span>

- [<span data-ttu-id="270b2-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="270b2-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="270b2-123">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="270b2-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)