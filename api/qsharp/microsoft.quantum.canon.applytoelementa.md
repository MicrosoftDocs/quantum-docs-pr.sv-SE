---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850758"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="d4a0f-102">ApplyToElementA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d4a0f-102">ApplyToElementA operation</span></span>

<span data-ttu-id="d4a0f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4a0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4a0f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4a0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4a0f-105">Tillämpar en åtgärd på ett angivet element i en matris.</span><span class="sxs-lookup"><span data-stu-id="d4a0f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="d4a0f-106">Description</span><span class="sxs-lookup"><span data-stu-id="d4a0f-106">Description</span></span>

<span data-ttu-id="d4a0f-107">En åtgärd `op` , ett index `index` och en matris med mål `targets` , gäller `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="d4a0f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="d4a0f-108">Indata</span><span class="sxs-lookup"><span data-stu-id="d4a0f-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d4a0f-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="d4a0f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d4a0f-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d4a0f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="d4a0f-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4a0f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4a0f-112">Ett index i matrisen med mål.</span><span class="sxs-lookup"><span data-stu-id="d4a0f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d4a0f-113">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="d4a0f-113">targets : 'T[]</span></span>

<span data-ttu-id="d4a0f-114">En matris med möjliga mål för `op` .</span><span class="sxs-lookup"><span data-stu-id="d4a0f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4a0f-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4a0f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4a0f-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d4a0f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4a0f-117">Inte</span><span class="sxs-lookup"><span data-stu-id="d4a0f-117">'T</span></span>

<span data-ttu-id="d4a0f-118">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d4a0f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a0f-119">Se även</span><span class="sxs-lookup"><span data-stu-id="d4a0f-119">See Also</span></span>

- [<span data-ttu-id="d4a0f-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="d4a0f-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="d4a0f-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="d4a0f-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="d4a0f-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="d4a0f-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)