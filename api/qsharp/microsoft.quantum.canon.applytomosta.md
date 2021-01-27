---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850576"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="1f51f-102">ApplyToMostA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1f51f-102">ApplyToMostA operation</span></span>

<span data-ttu-id="1f51f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f51f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f51f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f51f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f51f-105">Tillämpar en åtgärd på alla utom det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="1f51f-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="1f51f-106">Description</span><span class="sxs-lookup"><span data-stu-id="1f51f-106">Description</span></span>

<span data-ttu-id="1f51f-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1f51f-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1f51f-108">Indata</span><span class="sxs-lookup"><span data-stu-id="1f51f-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="1f51f-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="1f51f-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1f51f-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1f51f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1f51f-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="1f51f-111">targets : 'T[]</span></span>

<span data-ttu-id="1f51f-112">En matris med mål, varav alla utom den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="1f51f-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f51f-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f51f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f51f-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1f51f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f51f-115">Inte</span><span class="sxs-lookup"><span data-stu-id="1f51f-115">'T</span></span>

<span data-ttu-id="1f51f-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1f51f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f51f-117">Se även</span><span class="sxs-lookup"><span data-stu-id="1f51f-117">See Also</span></span>

- [<span data-ttu-id="1f51f-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="1f51f-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="1f51f-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="1f51f-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="1f51f-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="1f51f-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)