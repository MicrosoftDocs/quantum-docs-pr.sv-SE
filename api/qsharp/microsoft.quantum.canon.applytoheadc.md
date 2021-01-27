---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850632"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="2963c-102">ApplyToHeadC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2963c-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="2963c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2963c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2963c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2963c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2963c-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="2963c-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="2963c-106">Description</span><span class="sxs-lookup"><span data-stu-id="2963c-106">Description</span></span>

<span data-ttu-id="2963c-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2963c-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2963c-108">Indata</span><span class="sxs-lookup"><span data-stu-id="2963c-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="2963c-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="2963c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2963c-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="2963c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2963c-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="2963c-111">targets : 'T[]</span></span>

<span data-ttu-id="2963c-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="2963c-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2963c-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2963c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2963c-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2963c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2963c-115">Inte</span><span class="sxs-lookup"><span data-stu-id="2963c-115">'T</span></span>

<span data-ttu-id="2963c-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="2963c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2963c-117">Se även</span><span class="sxs-lookup"><span data-stu-id="2963c-117">See Also</span></span>

- [<span data-ttu-id="2963c-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="2963c-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="2963c-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="2963c-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="2963c-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="2963c-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)