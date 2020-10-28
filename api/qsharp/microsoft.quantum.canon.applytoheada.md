---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729166"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="e6953-102">ApplyToHeadA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e6953-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="e6953-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6953-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6953-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6953-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6953-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="e6953-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e6953-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6953-106">Description</span></span>

<span data-ttu-id="e6953-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e6953-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e6953-108">Indata</span><span class="sxs-lookup"><span data-stu-id="e6953-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="e6953-109">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="e6953-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e6953-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e6953-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e6953-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="e6953-111">targets : 'T[]</span></span>

<span data-ttu-id="e6953-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="e6953-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6953-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6953-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e6953-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e6953-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6953-115">Inte</span><span class="sxs-lookup"><span data-stu-id="e6953-115">'T</span></span>

<span data-ttu-id="e6953-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e6953-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6953-117">Se även</span><span class="sxs-lookup"><span data-stu-id="e6953-117">See Also</span></span>

- [<span data-ttu-id="e6953-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="e6953-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="e6953-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e6953-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e6953-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="e6953-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)