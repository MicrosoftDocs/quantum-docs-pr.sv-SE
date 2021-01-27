---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841324"
---
# <a name="applytohead-operation"></a><span data-ttu-id="ab9cb-102">ApplyToHead-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ab9cb-102">ApplyToHead operation</span></span>

<span data-ttu-id="ab9cb-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab9cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab9cb-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab9cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab9cb-105">Tillämpar en åtgärd på det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="ab9cb-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ab9cb-106">Description</span><span class="sxs-lookup"><span data-stu-id="ab9cb-106">Description</span></span>

<span data-ttu-id="ab9cb-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ab9cb-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ab9cb-108">Indata</span><span class="sxs-lookup"><span data-stu-id="ab9cb-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ab9cb-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab9cb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ab9cb-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ab9cb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ab9cb-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="ab9cb-111">targets : 'T[]</span></span>

<span data-ttu-id="ab9cb-112">En matris med mål, varav den första ska tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="ab9cb-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab9cb-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab9cb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab9cb-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ab9cb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab9cb-115">Inte</span><span class="sxs-lookup"><span data-stu-id="ab9cb-115">'T</span></span>

<span data-ttu-id="ab9cb-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ab9cb-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="ab9cb-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="ab9cb-117">Example</span></span>

<span data-ttu-id="ab9cb-118">Följande Q #-kodfragment är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="ab9cb-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="ab9cb-119">Se även</span><span class="sxs-lookup"><span data-stu-id="ab9cb-119">See Also</span></span>

- [<span data-ttu-id="ab9cb-120">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="ab9cb-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="ab9cb-121">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="ab9cb-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="ab9cb-122">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="ab9cb-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)