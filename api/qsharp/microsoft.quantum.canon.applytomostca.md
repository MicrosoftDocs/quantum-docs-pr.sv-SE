---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841317"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="162e8-102">ApplyToMostCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="162e8-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="162e8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="162e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="162e8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="162e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="162e8-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="162e8-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="162e8-106">Description</span><span class="sxs-lookup"><span data-stu-id="162e8-106">Description</span></span>

<span data-ttu-id="162e8-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="162e8-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="162e8-108">Indata</span><span class="sxs-lookup"><span data-stu-id="162e8-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="162e8-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="162e8-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="162e8-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="162e8-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="162e8-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="162e8-111">targets : 'T[]</span></span>

<span data-ttu-id="162e8-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="162e8-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="162e8-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="162e8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="162e8-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="162e8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="162e8-115">Inte</span><span class="sxs-lookup"><span data-stu-id="162e8-115">'T</span></span>

<span data-ttu-id="162e8-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="162e8-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="162e8-117">Se även</span><span class="sxs-lookup"><span data-stu-id="162e8-117">See Also</span></span>

- [<span data-ttu-id="162e8-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="162e8-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="162e8-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="162e8-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="162e8-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="162e8-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)