---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850746"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="bed09-102">ApplyToElementC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bed09-102">ApplyToElementC operation</span></span>

<span data-ttu-id="bed09-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bed09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bed09-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bed09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bed09-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="bed09-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="bed09-106">Description</span><span class="sxs-lookup"><span data-stu-id="bed09-106">Description</span></span>

<span data-ttu-id="bed09-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="bed09-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="bed09-108">Indata</span><span class="sxs-lookup"><span data-stu-id="bed09-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bed09-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="bed09-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bed09-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bed09-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="bed09-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bed09-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bed09-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="bed09-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bed09-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="bed09-113">targets : 'T[]</span></span>

<span data-ttu-id="bed09-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="bed09-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bed09-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bed09-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bed09-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bed09-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bed09-117">Inte</span><span class="sxs-lookup"><span data-stu-id="bed09-117">'T</span></span>

<span data-ttu-id="bed09-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bed09-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bed09-119">Se även</span><span class="sxs-lookup"><span data-stu-id="bed09-119">See Also</span></span>

- [<span data-ttu-id="bed09-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="bed09-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="bed09-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="bed09-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="bed09-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="bed09-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)