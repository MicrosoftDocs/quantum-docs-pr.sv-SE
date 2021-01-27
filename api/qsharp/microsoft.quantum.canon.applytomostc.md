---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850563"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="5701a-102">ApplyToMostC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5701a-102">ApplyToMostC operation</span></span>

<span data-ttu-id="5701a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5701a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5701a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5701a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5701a-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="5701a-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="5701a-106">Description</span><span class="sxs-lookup"><span data-stu-id="5701a-106">Description</span></span>

<span data-ttu-id="5701a-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="5701a-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5701a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="5701a-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="5701a-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="5701a-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5701a-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="5701a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5701a-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="5701a-111">targets : 'T[]</span></span>

<span data-ttu-id="5701a-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="5701a-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5701a-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5701a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5701a-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5701a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5701a-115">Inte</span><span class="sxs-lookup"><span data-stu-id="5701a-115">'T</span></span>

<span data-ttu-id="5701a-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="5701a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5701a-117">Se även</span><span class="sxs-lookup"><span data-stu-id="5701a-117">See Also</span></span>

- [<span data-ttu-id="5701a-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="5701a-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="5701a-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="5701a-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="5701a-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="5701a-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)