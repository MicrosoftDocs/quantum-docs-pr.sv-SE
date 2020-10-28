---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729157"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="80364-102">ApplyToHeadCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="80364-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="80364-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80364-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80364-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80364-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80364-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="80364-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="80364-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="80364-106">Description</span></span>

<span data-ttu-id="80364-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="80364-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="80364-108">Indata</span><span class="sxs-lookup"><span data-stu-id="80364-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="80364-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="80364-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="80364-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="80364-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="80364-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="80364-111">targets : 'T[]</span></span>

<span data-ttu-id="80364-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="80364-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80364-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80364-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80364-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="80364-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80364-115">Inte</span><span class="sxs-lookup"><span data-stu-id="80364-115">'T</span></span>

<span data-ttu-id="80364-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="80364-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="80364-117">Se även</span><span class="sxs-lookup"><span data-stu-id="80364-117">See Also</span></span>

- [<span data-ttu-id="80364-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="80364-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="80364-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="80364-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="80364-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="80364-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)