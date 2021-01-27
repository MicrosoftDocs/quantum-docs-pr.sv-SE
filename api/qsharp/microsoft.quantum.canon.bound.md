---
uid: Microsoft.Quantum.Canon.Bound
title: Bound-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841053"
---
# <a name="bound-function"></a><span data-ttu-id="d19b9-102">Bound-funktion</span><span class="sxs-lookup"><span data-stu-id="d19b9-102">Bound function</span></span>

<span data-ttu-id="d19b9-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d19b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d19b9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d19b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d19b9-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="d19b9-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="d19b9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d19b9-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="d19b9-107">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="d19b9-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="d19b9-108">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="d19b9-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="d19b9-109">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d19b9-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d19b9-110">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="d19b9-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d19b9-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d19b9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d19b9-112">Inte</span><span class="sxs-lookup"><span data-stu-id="d19b9-112">'T</span></span>

<span data-ttu-id="d19b9-113">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="d19b9-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="d19b9-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="d19b9-114">Example</span></span>

<span data-ttu-id="d19b9-115">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="d19b9-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="d19b9-116">och</span><span class="sxs-lookup"><span data-stu-id="d19b9-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="d19b9-117">Se även</span><span class="sxs-lookup"><span data-stu-id="d19b9-117">See Also</span></span>

- [<span data-ttu-id="d19b9-118">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="d19b9-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="d19b9-119">Microsoft. Quantum. Canon. Boundas</span><span class="sxs-lookup"><span data-stu-id="d19b9-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="d19b9-120">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="d19b9-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)