---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729154"
---
# <a name="applytomost-operation"></a><span data-ttu-id="33094-102">ApplyToMost-åtgärd</span><span class="sxs-lookup"><span data-stu-id="33094-102">ApplyToMost operation</span></span>

<span data-ttu-id="33094-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33094-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33094-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33094-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33094-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="33094-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="33094-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33094-106">Description</span></span>

<span data-ttu-id="33094-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="33094-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="33094-108">Indata</span><span class="sxs-lookup"><span data-stu-id="33094-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="33094-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33094-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="33094-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="33094-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="33094-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="33094-111">targets : 'T[]</span></span>

<span data-ttu-id="33094-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="33094-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33094-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33094-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33094-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="33094-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33094-115">Inte</span><span class="sxs-lookup"><span data-stu-id="33094-115">'T</span></span>

<span data-ttu-id="33094-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="33094-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="33094-117">Se även</span><span class="sxs-lookup"><span data-stu-id="33094-117">See Also</span></span>

- [<span data-ttu-id="33094-118">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="33094-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="33094-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="33094-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="33094-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="33094-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)