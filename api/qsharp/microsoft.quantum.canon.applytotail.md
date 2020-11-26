---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207980"
---
# <a name="applytotail-operation"></a><span data-ttu-id="cc72a-102">ApplyToTail-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cc72a-102">ApplyToTail operation</span></span>

<span data-ttu-id="cc72a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc72a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc72a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc72a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc72a-105">Tillämpar en åtgärd på det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="cc72a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="cc72a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cc72a-106">Description</span></span>

<span data-ttu-id="cc72a-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="cc72a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="cc72a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="cc72a-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="cc72a-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc72a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cc72a-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="cc72a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cc72a-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="cc72a-111">targets : 'T[]</span></span>

<span data-ttu-id="cc72a-112">En matris med mål som den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="cc72a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc72a-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc72a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cc72a-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="cc72a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc72a-115">Inte</span><span class="sxs-lookup"><span data-stu-id="cc72a-115">'T</span></span>

<span data-ttu-id="cc72a-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="cc72a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc72a-117">Se även</span><span class="sxs-lookup"><span data-stu-id="cc72a-117">See Also</span></span>

- [<span data-ttu-id="cc72a-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="cc72a-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="cc72a-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="cc72a-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="cc72a-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="cc72a-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)