---
uid: Microsoft.Quantum.Canon.Delayed
title: Fördröjd funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728737"
---
# <a name="delayed-function"></a><span data-ttu-id="aad6d-102">Fördröjd funktion</span><span class="sxs-lookup"><span data-stu-id="aad6d-102">Delayed function</span></span>

<span data-ttu-id="aad6d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aad6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aad6d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aad6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aad6d-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="aad6d-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="aad6d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="aad6d-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="aad6d-107">OP: t => ' U</span><span class="sxs-lookup"><span data-stu-id="aad6d-107">op : 'T => 'U</span></span> 

<span data-ttu-id="aad6d-108">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="aad6d-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="aad6d-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="aad6d-109">arg : 'T</span></span>

<span data-ttu-id="aad6d-110">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="aad6d-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="aad6d-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="aad6d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="aad6d-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="aad6d-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aad6d-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="aad6d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aad6d-114">Inte</span><span class="sxs-lookup"><span data-stu-id="aad6d-114">'T</span></span>

<span data-ttu-id="aad6d-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="aad6d-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="aad6d-116">' U</span><span class="sxs-lookup"><span data-stu-id="aad6d-116">'U</span></span>

<span data-ttu-id="aad6d-117">Retur typen för åtgärden som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="aad6d-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="aad6d-118">Se även</span><span class="sxs-lookup"><span data-stu-id="aad6d-118">See Also</span></span>

- [<span data-ttu-id="aad6d-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="aad6d-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="aad6d-120">Microsoft. Quantum. Canon. försenat</span><span class="sxs-lookup"><span data-stu-id="aad6d-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="aad6d-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="aad6d-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="aad6d-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="aad6d-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)