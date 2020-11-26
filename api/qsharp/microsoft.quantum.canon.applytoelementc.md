---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217585"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="36ae9-102">ApplyToElementC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="36ae9-102">ApplyToElementC operation</span></span>

<span data-ttu-id="36ae9-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36ae9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36ae9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36ae9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36ae9-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="36ae9-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="36ae9-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="36ae9-106">Description</span></span>

<span data-ttu-id="36ae9-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="36ae9-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="36ae9-108">Indata</span><span class="sxs-lookup"><span data-stu-id="36ae9-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="36ae9-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="36ae9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="36ae9-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="36ae9-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="36ae9-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36ae9-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36ae9-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="36ae9-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="36ae9-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="36ae9-113">targets : 'T[]</span></span>

<span data-ttu-id="36ae9-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="36ae9-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36ae9-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36ae9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="36ae9-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="36ae9-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36ae9-117">Inte</span><span class="sxs-lookup"><span data-stu-id="36ae9-117">'T</span></span>

<span data-ttu-id="36ae9-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="36ae9-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="36ae9-119">Se även</span><span class="sxs-lookup"><span data-stu-id="36ae9-119">See Also</span></span>

- [<span data-ttu-id="36ae9-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="36ae9-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="36ae9-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="36ae9-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="36ae9-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="36ae9-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)