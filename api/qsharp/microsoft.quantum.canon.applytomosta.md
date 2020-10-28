---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729145"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="ef7d4-102">ApplyToMostA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ef7d4-102">ApplyToMostA operation</span></span>

<span data-ttu-id="ef7d4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef7d4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef7d4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef7d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef7d4-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="ef7d4-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ef7d4-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef7d4-106">Description</span></span>

<span data-ttu-id="ef7d4-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ef7d4-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ef7d4-108">Indata</span><span class="sxs-lookup"><span data-stu-id="ef7d4-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="ef7d4-109">OP: ' t [] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="ef7d4-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ef7d4-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ef7d4-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ef7d4-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="ef7d4-111">targets : 'T[]</span></span>

<span data-ttu-id="ef7d4-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="ef7d4-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef7d4-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef7d4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ef7d4-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ef7d4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ef7d4-115">Inte</span><span class="sxs-lookup"><span data-stu-id="ef7d4-115">'T</span></span>

<span data-ttu-id="ef7d4-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ef7d4-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef7d4-117">Se även</span><span class="sxs-lookup"><span data-stu-id="ef7d4-117">See Also</span></span>

- [<span data-ttu-id="ef7d4-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="ef7d4-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="ef7d4-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="ef7d4-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="ef7d4-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="ef7d4-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)