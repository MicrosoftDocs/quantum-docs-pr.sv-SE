---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208473"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="de678-102">ApplyToMostC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="de678-102">ApplyToMostC operation</span></span>

<span data-ttu-id="de678-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="de678-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="de678-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de678-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de678-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="de678-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="de678-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="de678-106">Description</span></span>

<span data-ttu-id="de678-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="de678-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="de678-108">Indata</span><span class="sxs-lookup"><span data-stu-id="de678-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="de678-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="de678-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="de678-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="de678-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="de678-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="de678-111">targets : 'T[]</span></span>

<span data-ttu-id="de678-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="de678-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de678-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de678-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="de678-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="de678-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="de678-115">Inte</span><span class="sxs-lookup"><span data-stu-id="de678-115">'T</span></span>

<span data-ttu-id="de678-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="de678-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="de678-117">Se även</span><span class="sxs-lookup"><span data-stu-id="de678-117">See Also</span></span>

- [<span data-ttu-id="de678-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="de678-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="de678-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="de678-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="de678-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="de678-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)