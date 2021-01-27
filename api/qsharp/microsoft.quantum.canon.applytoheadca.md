---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850605"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="a9133-102">ApplyToHeadCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a9133-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="a9133-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9133-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9133-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9133-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9133-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="a9133-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a9133-106">Description</span><span class="sxs-lookup"><span data-stu-id="a9133-106">Description</span></span>

<span data-ttu-id="a9133-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a9133-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a9133-108">Indata</span><span class="sxs-lookup"><span data-stu-id="a9133-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="a9133-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="a9133-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a9133-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a9133-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a9133-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="a9133-111">targets : 'T[]</span></span>

<span data-ttu-id="a9133-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="a9133-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9133-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9133-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9133-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a9133-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9133-115">Inte</span><span class="sxs-lookup"><span data-stu-id="a9133-115">'T</span></span>

<span data-ttu-id="a9133-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a9133-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9133-117">Se även</span><span class="sxs-lookup"><span data-stu-id="a9133-117">See Also</span></span>

- [<span data-ttu-id="a9133-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="a9133-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="a9133-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="a9133-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="a9133-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="a9133-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)