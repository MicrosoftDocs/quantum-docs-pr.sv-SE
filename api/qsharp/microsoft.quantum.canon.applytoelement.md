---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729274"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="df087-102">ApplyToElement-åtgärd</span><span class="sxs-lookup"><span data-stu-id="df087-102">ApplyToElement operation</span></span>

<span data-ttu-id="df087-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df087-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df087-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df087-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df087-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="df087-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="df087-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="df087-106">Description</span></span>

<span data-ttu-id="df087-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="df087-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="df087-108">Indata</span><span class="sxs-lookup"><span data-stu-id="df087-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="df087-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df087-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="df087-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="df087-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="df087-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df087-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df087-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="df087-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="df087-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="df087-113">targets : 'T[]</span></span>

<span data-ttu-id="df087-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="df087-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df087-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df087-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="df087-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="df087-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df087-117">Inte</span><span class="sxs-lookup"><span data-stu-id="df087-117">'T</span></span>

<span data-ttu-id="df087-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="df087-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="df087-119">Se även</span><span class="sxs-lookup"><span data-stu-id="df087-119">See Also</span></span>

- [<span data-ttu-id="df087-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="df087-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="df087-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="df087-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="df087-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="df087-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)