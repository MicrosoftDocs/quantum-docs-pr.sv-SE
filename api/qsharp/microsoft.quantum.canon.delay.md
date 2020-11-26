---
uid: Microsoft.Quantum.Canon.Delay
title: Fördröjnings åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216514"
---
# <a name="delay-operation"></a><span data-ttu-id="9d34e-102">Fördröjnings åtgärd</span><span class="sxs-lookup"><span data-stu-id="9d34e-102">Delay operation</span></span>

<span data-ttu-id="9d34e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d34e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d34e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d34e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d34e-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="9d34e-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="9d34e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9d34e-106">Description</span></span>

<span data-ttu-id="9d34e-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="9d34e-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="9d34e-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="9d34e-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="9d34e-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="9d34e-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="9d34e-110">Indata</span><span class="sxs-lookup"><span data-stu-id="9d34e-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="9d34e-111">OP: t => ' U</span><span class="sxs-lookup"><span data-stu-id="9d34e-111">op : 'T => 'U</span></span> 

<span data-ttu-id="9d34e-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="9d34e-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="9d34e-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="9d34e-113">arg : 'T</span></span>

<span data-ttu-id="9d34e-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="9d34e-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="9d34e-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d34e-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="9d34e-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="9d34e-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="9d34e-117">Utdata: ' U</span><span class="sxs-lookup"><span data-stu-id="9d34e-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9d34e-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9d34e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d34e-119">Inte</span><span class="sxs-lookup"><span data-stu-id="9d34e-119">'T</span></span>

<span data-ttu-id="9d34e-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="9d34e-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="9d34e-121">' U</span><span class="sxs-lookup"><span data-stu-id="9d34e-121">'U</span></span>

<span data-ttu-id="9d34e-122">Retur typen för åtgärden som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="9d34e-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d34e-123">Se även</span><span class="sxs-lookup"><span data-stu-id="9d34e-123">See Also</span></span>

- [<span data-ttu-id="9d34e-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="9d34e-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="9d34e-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="9d34e-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="9d34e-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="9d34e-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="9d34e-127">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="9d34e-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)