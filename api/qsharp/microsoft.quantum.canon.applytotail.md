---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850440"
---
# <a name="applytotail-operation"></a><span data-ttu-id="036cf-102">ApplyToTail-åtgärd</span><span class="sxs-lookup"><span data-stu-id="036cf-102">ApplyToTail operation</span></span>

<span data-ttu-id="036cf-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="036cf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="036cf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="036cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="036cf-105">Tillämpar en åtgärd på det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="036cf-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="036cf-106">Description</span><span class="sxs-lookup"><span data-stu-id="036cf-106">Description</span></span>

<span data-ttu-id="036cf-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="036cf-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="036cf-108">Indata</span><span class="sxs-lookup"><span data-stu-id="036cf-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="036cf-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="036cf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="036cf-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="036cf-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="036cf-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="036cf-111">targets : 'T[]</span></span>

<span data-ttu-id="036cf-112">En matris med mål som den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="036cf-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="036cf-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="036cf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="036cf-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="036cf-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="036cf-115">Inte</span><span class="sxs-lookup"><span data-stu-id="036cf-115">'T</span></span>

<span data-ttu-id="036cf-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="036cf-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="036cf-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="036cf-117">Example</span></span>

<span data-ttu-id="036cf-118">Följande Q #-kodfragment är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="036cf-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="036cf-119">Se även</span><span class="sxs-lookup"><span data-stu-id="036cf-119">See Also</span></span>

- [<span data-ttu-id="036cf-120">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="036cf-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="036cf-121">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="036cf-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="036cf-122">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="036cf-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)