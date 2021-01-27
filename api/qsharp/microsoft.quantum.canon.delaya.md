---
uid: Microsoft.Quantum.Canon.DelayA
title: Åtgärden fördröja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c7385cfcdf782347feb8d95311205a9311f4c929
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840671"
---
# <a name="delaya-operation"></a><span data-ttu-id="aa3c1-102">Åtgärden fördröja</span><span class="sxs-lookup"><span data-stu-id="aa3c1-102">DelayA operation</span></span>

<span data-ttu-id="aa3c1-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa3c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa3c1-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa3c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa3c1-105">Tillämpar en viss åtgärd med en fördröjning.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="aa3c1-106">Description</span><span class="sxs-lookup"><span data-stu-id="aa3c1-106">Description</span></span>

<span data-ttu-id="aa3c1-107">Vid en åtgärd och indata för åtgärden tillämpas åtgärden när ytterligare indata har angetts.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="aa3c1-108">I synnerhet `Delay(op, arg, _)` är uttrycket en åtgärd som gäller `op` `arg` vid anrop.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="aa3c1-109">Uttrycket `Delay(op,arg,_)` kan försena tillämpningen av `op` .</span><span class="sxs-lookup"><span data-stu-id="aa3c1-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="aa3c1-110">Indata</span><span class="sxs-lookup"><span data-stu-id="aa3c1-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="aa3c1-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="aa3c1-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="aa3c1-112">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="aa3c1-113">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="aa3c1-113">arg : 'T</span></span>

<span data-ttu-id="aa3c1-114">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="aa3c1-115">AUX: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3c1-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="aa3c1-116">Argumentet som används för att försena programmets åtgärd genom att använda partiellt program.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa3c1-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3c1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aa3c1-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="aa3c1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa3c1-119">Inte</span><span class="sxs-lookup"><span data-stu-id="aa3c1-119">'T</span></span>

<span data-ttu-id="aa3c1-120">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa3c1-121">Se även</span><span class="sxs-lookup"><span data-stu-id="aa3c1-121">See Also</span></span>

- [<span data-ttu-id="aa3c1-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="aa3c1-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="aa3c1-123">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="aa3c1-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)