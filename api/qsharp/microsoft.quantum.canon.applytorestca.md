---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729085"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="99391-102">ApplyToRestCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="99391-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="99391-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99391-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99391-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99391-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99391-105">Tillämpar en åtgärd på alla utom det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="99391-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="99391-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="99391-106">Description</span></span>

<span data-ttu-id="99391-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="99391-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="99391-108">Indata</span><span class="sxs-lookup"><span data-stu-id="99391-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="99391-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="99391-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="99391-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="99391-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="99391-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="99391-111">targets : 'T[]</span></span>

<span data-ttu-id="99391-112">En matris med mål, varav alla utom den första kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="99391-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99391-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99391-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99391-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="99391-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99391-115">Inte</span><span class="sxs-lookup"><span data-stu-id="99391-115">'T</span></span>

<span data-ttu-id="99391-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="99391-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="99391-117">Se även</span><span class="sxs-lookup"><span data-stu-id="99391-117">See Also</span></span>

- [<span data-ttu-id="99391-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="99391-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="99391-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="99391-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="99391-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="99391-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)