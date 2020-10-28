---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729247"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="bdc0d-102">ApplyToElementCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bdc0d-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="bdc0d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdc0d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdc0d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdc0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdc0d-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="bdc0d-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="bdc0d-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bdc0d-106">Description</span></span>

<span data-ttu-id="bdc0d-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="bdc0d-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="bdc0d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="bdc0d-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="bdc0d-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="bdc0d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bdc0d-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bdc0d-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="bdc0d-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdc0d-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdc0d-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="bdc0d-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bdc0d-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="bdc0d-113">targets : 'T[]</span></span>

<span data-ttu-id="bdc0d-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="bdc0d-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdc0d-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdc0d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bdc0d-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bdc0d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bdc0d-117">Inte</span><span class="sxs-lookup"><span data-stu-id="bdc0d-117">'T</span></span>

<span data-ttu-id="bdc0d-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bdc0d-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdc0d-119">Se även</span><span class="sxs-lookup"><span data-stu-id="bdc0d-119">See Also</span></span>

- [<span data-ttu-id="bdc0d-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="bdc0d-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="bdc0d-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="bdc0d-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="bdc0d-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="bdc0d-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)