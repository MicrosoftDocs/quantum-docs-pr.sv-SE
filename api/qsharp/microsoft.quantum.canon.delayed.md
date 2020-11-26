---
uid: Microsoft.Quantum.Canon.Delayed
title: Fördröjd funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216463"
---
# <a name="delayed-function"></a><span data-ttu-id="e6cf5-102">Fördröjd funktion</span><span class="sxs-lookup"><span data-stu-id="e6cf5-102">Delayed function</span></span>

<span data-ttu-id="e6cf5-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6cf5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6cf5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6cf5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6cf5-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="e6cf5-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="e6cf5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e6cf5-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="e6cf5-107">OP: t => ' U</span><span class="sxs-lookup"><span data-stu-id="e6cf5-107">op : 'T => 'U</span></span> 

<span data-ttu-id="e6cf5-108">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e6cf5-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="e6cf5-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="e6cf5-109">arg : 'T</span></span>

<span data-ttu-id="e6cf5-110">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e6cf5-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="e6cf5-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="e6cf5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="e6cf5-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="e6cf5-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6cf5-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e6cf5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6cf5-114">Inte</span><span class="sxs-lookup"><span data-stu-id="e6cf5-114">'T</span></span>

<span data-ttu-id="e6cf5-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="e6cf5-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="e6cf5-116">' U</span><span class="sxs-lookup"><span data-stu-id="e6cf5-116">'U</span></span>

<span data-ttu-id="e6cf5-117">Retur typen för åtgärden som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="e6cf5-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6cf5-118">Se även</span><span class="sxs-lookup"><span data-stu-id="e6cf5-118">See Also</span></span>

- [<span data-ttu-id="e6cf5-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="e6cf5-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="e6cf5-120">Microsoft. Quantum. Canon. försenat</span><span class="sxs-lookup"><span data-stu-id="e6cf5-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="e6cf5-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="e6cf5-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="e6cf5-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e6cf5-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)