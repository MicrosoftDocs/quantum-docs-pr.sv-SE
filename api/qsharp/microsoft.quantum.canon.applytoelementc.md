---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729250"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="1172e-102">ApplyToElementC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1172e-102">ApplyToElementC operation</span></span>

<span data-ttu-id="1172e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1172e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1172e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1172e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1172e-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="1172e-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="1172e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1172e-106">Description</span></span>

<span data-ttu-id="1172e-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="1172e-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="1172e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="1172e-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="1172e-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="1172e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="1172e-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1172e-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="1172e-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1172e-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1172e-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="1172e-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1172e-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="1172e-113">targets : 'T[]</span></span>

<span data-ttu-id="1172e-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="1172e-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1172e-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1172e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1172e-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1172e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1172e-117">Inte</span><span class="sxs-lookup"><span data-stu-id="1172e-117">'T</span></span>

<span data-ttu-id="1172e-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1172e-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1172e-119">Se även</span><span class="sxs-lookup"><span data-stu-id="1172e-119">See Also</span></span>

- [<span data-ttu-id="1172e-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="1172e-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="1172e-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="1172e-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="1172e-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="1172e-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)