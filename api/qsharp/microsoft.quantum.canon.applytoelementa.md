---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208881"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="bb6e0-102">ApplyToElementA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bb6e0-102">ApplyToElementA operation</span></span>

<span data-ttu-id="bb6e0-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb6e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb6e0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb6e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb6e0-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="bb6e0-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="bb6e0-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bb6e0-106">Description</span></span>

<span data-ttu-id="bb6e0-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="bb6e0-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="bb6e0-108">Indata</span><span class="sxs-lookup"><span data-stu-id="bb6e0-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="bb6e0-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="bb6e0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bb6e0-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bb6e0-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="bb6e0-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb6e0-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb6e0-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="bb6e0-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bb6e0-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="bb6e0-113">targets : 'T[]</span></span>

<span data-ttu-id="bb6e0-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="bb6e0-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb6e0-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb6e0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bb6e0-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bb6e0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb6e0-117">Inte</span><span class="sxs-lookup"><span data-stu-id="bb6e0-117">'T</span></span>

<span data-ttu-id="bb6e0-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bb6e0-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb6e0-119">Se även</span><span class="sxs-lookup"><span data-stu-id="bb6e0-119">See Also</span></span>

- [<span data-ttu-id="bb6e0-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="bb6e0-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="bb6e0-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="bb6e0-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="bb6e0-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="bb6e0-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)