---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208643"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="c8e39-102">ApplyToHeadA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c8e39-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="c8e39-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8e39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8e39-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8e39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8e39-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="c8e39-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c8e39-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8e39-106">Description</span></span>

<span data-ttu-id="c8e39-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c8e39-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c8e39-108">Indata</span><span class="sxs-lookup"><span data-stu-id="c8e39-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="c8e39-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="c8e39-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c8e39-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c8e39-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c8e39-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="c8e39-111">targets : 'T[]</span></span>

<span data-ttu-id="c8e39-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="c8e39-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8e39-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8e39-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c8e39-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c8e39-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8e39-115">Inte</span><span class="sxs-lookup"><span data-stu-id="c8e39-115">'T</span></span>

<span data-ttu-id="c8e39-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c8e39-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8e39-117">Se även</span><span class="sxs-lookup"><span data-stu-id="c8e39-117">See Also</span></span>

- [<span data-ttu-id="c8e39-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c8e39-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c8e39-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="c8e39-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="c8e39-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c8e39-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)