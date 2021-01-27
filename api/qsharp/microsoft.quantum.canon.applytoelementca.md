---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841470"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="9f579-102">ApplyToElementCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9f579-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="9f579-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f579-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f579-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f579-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f579-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="9f579-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9f579-106">Description</span><span class="sxs-lookup"><span data-stu-id="9f579-106">Description</span></span>

<span data-ttu-id="9f579-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="9f579-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9f579-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9f579-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="9f579-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="9f579-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9f579-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="9f579-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9f579-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f579-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f579-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="9f579-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9f579-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="9f579-113">targets : 'T[]</span></span>

<span data-ttu-id="9f579-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="9f579-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f579-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f579-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9f579-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9f579-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f579-117">Inte</span><span class="sxs-lookup"><span data-stu-id="9f579-117">'T</span></span>

<span data-ttu-id="9f579-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="9f579-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f579-119">Se även</span><span class="sxs-lookup"><span data-stu-id="9f579-119">See Also</span></span>

- [<span data-ttu-id="9f579-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="9f579-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9f579-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="9f579-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="9f579-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="9f579-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)