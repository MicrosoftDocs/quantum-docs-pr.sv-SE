---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729046"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="05a2e-102">ApplyToTailA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="05a2e-102">ApplyToTailA operation</span></span>

<span data-ttu-id="05a2e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05a2e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05a2e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05a2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05a2e-105">Tillämpar en åtgärd på det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="05a2e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="05a2e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="05a2e-106">Description</span></span>

<span data-ttu-id="05a2e-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="05a2e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="05a2e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="05a2e-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="05a2e-109">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="05a2e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="05a2e-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="05a2e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="05a2e-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="05a2e-111">targets : 'T[]</span></span>

<span data-ttu-id="05a2e-112">En matris med mål som den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="05a2e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05a2e-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05a2e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="05a2e-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="05a2e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="05a2e-115">Inte</span><span class="sxs-lookup"><span data-stu-id="05a2e-115">'T</span></span>

<span data-ttu-id="05a2e-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="05a2e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="05a2e-117">Se även</span><span class="sxs-lookup"><span data-stu-id="05a2e-117">See Also</span></span>

- [<span data-ttu-id="05a2e-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="05a2e-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="05a2e-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="05a2e-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="05a2e-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="05a2e-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)