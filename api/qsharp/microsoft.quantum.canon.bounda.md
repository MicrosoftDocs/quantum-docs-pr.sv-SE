---
uid: Microsoft.Quantum.Canon.BoundA
title: Bindnings funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844546"
---
# <a name="bounda-function"></a><span data-ttu-id="cab6c-102">Bindnings funktion</span><span class="sxs-lookup"><span data-stu-id="cab6c-102">BoundA function</span></span>

<span data-ttu-id="cab6c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cab6c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cab6c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cab6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cab6c-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="cab6c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="cab6c-106">Modifieraren `A` anger att alla åtgärder i matrisen är adjointable.</span><span class="sxs-lookup"><span data-stu-id="cab6c-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="cab6c-107">Indata</span><span class="sxs-lookup"><span data-stu-id="cab6c-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="cab6c-108">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just []</span><span class="sxs-lookup"><span data-stu-id="cab6c-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="cab6c-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="cab6c-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="cab6c-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="cab6c-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cab6c-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="cab6c-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cab6c-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="cab6c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cab6c-113">Inte</span><span class="sxs-lookup"><span data-stu-id="cab6c-113">'T</span></span>

<span data-ttu-id="cab6c-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="cab6c-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="cab6c-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="cab6c-115">Example</span></span>

<span data-ttu-id="cab6c-116">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="cab6c-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="cab6c-117">och</span><span class="sxs-lookup"><span data-stu-id="cab6c-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="cab6c-118">Se även</span><span class="sxs-lookup"><span data-stu-id="cab6c-118">See Also</span></span>

- [<span data-ttu-id="cab6c-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="cab6c-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)