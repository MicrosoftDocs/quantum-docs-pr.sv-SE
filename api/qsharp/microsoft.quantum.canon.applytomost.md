---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850595"
---
# <a name="applytomost-operation"></a><span data-ttu-id="4939e-102">ApplyToMost-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4939e-102">ApplyToMost operation</span></span>

<span data-ttu-id="4939e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4939e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4939e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4939e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4939e-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="4939e-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4939e-106">Description</span><span class="sxs-lookup"><span data-stu-id="4939e-106">Description</span></span>

<span data-ttu-id="4939e-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4939e-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4939e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="4939e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4939e-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4939e-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4939e-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="4939e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4939e-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="4939e-111">targets : 'T[]</span></span>

<span data-ttu-id="4939e-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="4939e-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4939e-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4939e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4939e-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4939e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4939e-115">Inte</span><span class="sxs-lookup"><span data-stu-id="4939e-115">'T</span></span>

<span data-ttu-id="4939e-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="4939e-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="4939e-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="4939e-117">Example</span></span>

<span data-ttu-id="4939e-118">Följande Q #-kodfragment är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="4939e-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="4939e-119">Se även</span><span class="sxs-lookup"><span data-stu-id="4939e-119">See Also</span></span>

- [<span data-ttu-id="4939e-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="4939e-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="4939e-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="4939e-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="4939e-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="4939e-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)