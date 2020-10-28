---
uid: Microsoft.Quantum.Canon.Delay
title: Fördröjnings åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728764"
---
# <a name="delay-operation"></a><span data-ttu-id="66aaf-102">Fördröjnings åtgärd</span><span class="sxs-lookup"><span data-stu-id="66aaf-102">Delay operation</span></span>

<span data-ttu-id="66aaf-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="66aaf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="66aaf-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66aaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66aaf-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="66aaf-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="66aaf-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="66aaf-106">Description</span></span>

<span data-ttu-id="66aaf-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="66aaf-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="66aaf-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="66aaf-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="66aaf-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="66aaf-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="66aaf-110">Indata</span><span class="sxs-lookup"><span data-stu-id="66aaf-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="66aaf-111">OP: t => ' U</span><span class="sxs-lookup"><span data-stu-id="66aaf-111">op : 'T => 'U</span></span> 

<span data-ttu-id="66aaf-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="66aaf-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="66aaf-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="66aaf-113">arg : 'T</span></span>

<span data-ttu-id="66aaf-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="66aaf-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="66aaf-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66aaf-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="66aaf-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="66aaf-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="66aaf-117">Utdata: ' U</span><span class="sxs-lookup"><span data-stu-id="66aaf-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66aaf-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="66aaf-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66aaf-119">Inte</span><span class="sxs-lookup"><span data-stu-id="66aaf-119">'T</span></span>

<span data-ttu-id="66aaf-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="66aaf-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="66aaf-121">' U</span><span class="sxs-lookup"><span data-stu-id="66aaf-121">'U</span></span>

<span data-ttu-id="66aaf-122">Retur typen för åtgärden som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="66aaf-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="66aaf-123">Se även</span><span class="sxs-lookup"><span data-stu-id="66aaf-123">See Also</span></span>

- [<span data-ttu-id="66aaf-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="66aaf-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="66aaf-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="66aaf-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="66aaf-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="66aaf-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="66aaf-127">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="66aaf-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)