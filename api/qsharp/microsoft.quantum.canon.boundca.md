---
uid: Microsoft.Quantum.Canon.BoundCA
title: Funktionen BoundCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844519"
---
# <a name="boundca-function"></a><span data-ttu-id="fb15a-102">Funktionen BoundCA</span><span class="sxs-lookup"><span data-stu-id="fb15a-102">BoundCA function</span></span>

<span data-ttu-id="fb15a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fb15a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fb15a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb15a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb15a-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="fb15a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="fb15a-106">Modifieraren `CA` anger att alla åtgärder i matrisen är adjointable och kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="fb15a-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="fb15a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="fb15a-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="fb15a-108">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []</span><span class="sxs-lookup"><span data-stu-id="fb15a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="fb15a-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="fb15a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="fb15a-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="fb15a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fb15a-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="fb15a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fb15a-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fb15a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fb15a-113">Inte</span><span class="sxs-lookup"><span data-stu-id="fb15a-113">'T</span></span>

<span data-ttu-id="fb15a-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="fb15a-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="fb15a-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="fb15a-115">Example</span></span>

<span data-ttu-id="fb15a-116">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="fb15a-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="fb15a-117">och</span><span class="sxs-lookup"><span data-stu-id="fb15a-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="fb15a-118">Se även</span><span class="sxs-lookup"><span data-stu-id="fb15a-118">See Also</span></span>

- [<span data-ttu-id="fb15a-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="fb15a-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)