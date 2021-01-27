---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840623"
---
# <a name="delayca-operation"></a><span data-ttu-id="69057-102">DelayCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="69057-102">DelayCA operation</span></span>

<span data-ttu-id="69057-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69057-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69057-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69057-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69057-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="69057-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="69057-106">Description</span><span class="sxs-lookup"><span data-stu-id="69057-106">Description</span></span>

<span data-ttu-id="69057-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="69057-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="69057-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="69057-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="69057-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="69057-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="69057-110">Indata</span><span class="sxs-lookup"><span data-stu-id="69057-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="69057-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="69057-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="69057-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="69057-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="69057-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="69057-113">arg : 'T</span></span>

<span data-ttu-id="69057-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="69057-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="69057-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69057-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="69057-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="69057-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69057-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69057-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="69057-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="69057-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69057-119">Inte</span><span class="sxs-lookup"><span data-stu-id="69057-119">'T</span></span>

<span data-ttu-id="69057-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="69057-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="69057-121">Se även</span><span class="sxs-lookup"><span data-stu-id="69057-121">See Also</span></span>

- [<span data-ttu-id="69057-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="69057-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="69057-123">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="69057-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)