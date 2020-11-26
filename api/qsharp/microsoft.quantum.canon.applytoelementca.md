---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208864"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="27d08-102">ApplyToElementCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="27d08-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="27d08-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27d08-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27d08-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27d08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27d08-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="27d08-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="27d08-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="27d08-106">Description</span></span>

<span data-ttu-id="27d08-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="27d08-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="27d08-108">Indata</span><span class="sxs-lookup"><span data-stu-id="27d08-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="27d08-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="27d08-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="27d08-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="27d08-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="27d08-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27d08-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27d08-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="27d08-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="27d08-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="27d08-113">targets : 'T[]</span></span>

<span data-ttu-id="27d08-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="27d08-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27d08-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27d08-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27d08-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="27d08-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27d08-117">Inte</span><span class="sxs-lookup"><span data-stu-id="27d08-117">'T</span></span>

<span data-ttu-id="27d08-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="27d08-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="27d08-119">Se även</span><span class="sxs-lookup"><span data-stu-id="27d08-119">See Also</span></span>

- [<span data-ttu-id="27d08-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="27d08-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="27d08-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="27d08-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="27d08-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="27d08-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)