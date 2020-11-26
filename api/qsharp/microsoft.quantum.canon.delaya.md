---
uid: Microsoft.Quantum.Canon.DelayA
title: Åtgärden fördröja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207147"
---
# <a name="delaya-operation"></a><span data-ttu-id="6dd49-102">Åtgärden fördröja</span><span class="sxs-lookup"><span data-stu-id="6dd49-102">DelayA operation</span></span>

<span data-ttu-id="6dd49-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6dd49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6dd49-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6dd49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6dd49-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="6dd49-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="6dd49-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6dd49-106">Description</span></span>

<span data-ttu-id="6dd49-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="6dd49-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="6dd49-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="6dd49-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="6dd49-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="6dd49-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="6dd49-110">Indata</span><span class="sxs-lookup"><span data-stu-id="6dd49-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="6dd49-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="6dd49-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6dd49-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6dd49-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="6dd49-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="6dd49-113">arg : 'T</span></span>

<span data-ttu-id="6dd49-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="6dd49-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="6dd49-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6dd49-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="6dd49-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="6dd49-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6dd49-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6dd49-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6dd49-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6dd49-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6dd49-119">Inte</span><span class="sxs-lookup"><span data-stu-id="6dd49-119">'T</span></span>

<span data-ttu-id="6dd49-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="6dd49-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dd49-121">Se även</span><span class="sxs-lookup"><span data-stu-id="6dd49-121">See Also</span></span>

- [<span data-ttu-id="6dd49-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="6dd49-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="6dd49-123">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="6dd49-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)