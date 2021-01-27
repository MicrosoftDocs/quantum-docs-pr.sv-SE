---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850514"
---
# <a name="applytorest-operation"></a><span data-ttu-id="6cb7b-102">ApplyToRest-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6cb7b-102">ApplyToRest operation</span></span>

<span data-ttu-id="6cb7b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6cb7b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6cb7b-105">Tillämpar en åtgärd på alla utom det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6cb7b-106">Description</span><span class="sxs-lookup"><span data-stu-id="6cb7b-106">Description</span></span>

<span data-ttu-id="6cb7b-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6cb7b-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6cb7b-108">Indata</span><span class="sxs-lookup"><span data-stu-id="6cb7b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6cb7b-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6cb7b-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6cb7b-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="6cb7b-111">targets : 'T[]</span></span>

<span data-ttu-id="6cb7b-112">En matris med mål, varav alla utom den första kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="6cb7b-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6cb7b-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6cb7b-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6cb7b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6cb7b-115">Inte</span><span class="sxs-lookup"><span data-stu-id="6cb7b-115">'T</span></span>

<span data-ttu-id="6cb7b-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="6cb7b-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="6cb7b-117">Example</span></span>

<span data-ttu-id="6cb7b-118">Följande Q #-kodfragment är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="6cb7b-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="6cb7b-119">Se även</span><span class="sxs-lookup"><span data-stu-id="6cb7b-119">See Also</span></span>

- [<span data-ttu-id="6cb7b-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="6cb7b-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="6cb7b-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="6cb7b-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="6cb7b-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)