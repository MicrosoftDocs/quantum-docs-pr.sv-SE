---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208281"
---
# <a name="applytorest-operation"></a><span data-ttu-id="e8fb9-102">ApplyToRest-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e8fb9-102">ApplyToRest operation</span></span>

<span data-ttu-id="e8fb9-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e8fb9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e8fb9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8fb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8fb9-105">Tillämpar en åtgärd på alla utom det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="e8fb9-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e8fb9-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e8fb9-106">Description</span></span>

<span data-ttu-id="e8fb9-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e8fb9-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e8fb9-108">Indata</span><span class="sxs-lookup"><span data-stu-id="e8fb9-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e8fb9-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8fb9-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e8fb9-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e8fb9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e8fb9-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="e8fb9-111">targets : 'T[]</span></span>

<span data-ttu-id="e8fb9-112">En matris med mål, varav alla utom den första kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="e8fb9-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8fb9-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8fb9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8fb9-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e8fb9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8fb9-115">Inte</span><span class="sxs-lookup"><span data-stu-id="e8fb9-115">'T</span></span>

<span data-ttu-id="e8fb9-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e8fb9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8fb9-117">Se även</span><span class="sxs-lookup"><span data-stu-id="e8fb9-117">See Also</span></span>

- [<span data-ttu-id="e8fb9-118">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="e8fb9-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="e8fb9-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="e8fb9-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="e8fb9-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="e8fb9-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)