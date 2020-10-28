---
uid: Microsoft.Quantum.Canon.Bound
title: Bound-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728929"
---
# <a name="bound-function"></a><span data-ttu-id="e915c-102">Bound-funktion</span><span class="sxs-lookup"><span data-stu-id="e915c-102">Bound function</span></span>

<span data-ttu-id="e915c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e915c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e915c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e915c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e915c-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="e915c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="e915c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e915c-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="e915c-107">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="e915c-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="e915c-108">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="e915c-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="e915c-109">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e915c-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e915c-110">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="e915c-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e915c-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e915c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e915c-112">Inte</span><span class="sxs-lookup"><span data-stu-id="e915c-112">'T</span></span>

<span data-ttu-id="e915c-113">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="e915c-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="e915c-114">Se även</span><span class="sxs-lookup"><span data-stu-id="e915c-114">See Also</span></span>

- [<span data-ttu-id="e915c-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="e915c-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="e915c-116">Microsoft. Quantum. Canon. Boundas</span><span class="sxs-lookup"><span data-stu-id="e915c-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="e915c-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="e915c-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)