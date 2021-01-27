---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850499"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="cfb85-102">ApplyToRestC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cfb85-102">ApplyToRestC operation</span></span>

<span data-ttu-id="cfb85-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cfb85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cfb85-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfb85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfb85-105">Tillämpar en åtgärd på alla utom det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="cfb85-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="cfb85-106">Description</span><span class="sxs-lookup"><span data-stu-id="cfb85-106">Description</span></span>

<span data-ttu-id="cfb85-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="cfb85-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="cfb85-108">Indata</span><span class="sxs-lookup"><span data-stu-id="cfb85-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="cfb85-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="cfb85-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cfb85-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="cfb85-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cfb85-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="cfb85-111">targets : 'T[]</span></span>

<span data-ttu-id="cfb85-112">En matris med mål, varav alla utom den första kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="cfb85-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfb85-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfb85-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cfb85-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="cfb85-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfb85-115">Inte</span><span class="sxs-lookup"><span data-stu-id="cfb85-115">'T</span></span>

<span data-ttu-id="cfb85-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="cfb85-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfb85-117">Se även</span><span class="sxs-lookup"><span data-stu-id="cfb85-117">See Also</span></span>

- [<span data-ttu-id="cfb85-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="cfb85-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="cfb85-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="cfb85-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="cfb85-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="cfb85-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)