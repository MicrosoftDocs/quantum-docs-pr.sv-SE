---
uid: Microsoft.Quantum.Canon.BoundCA
title: Funktionen BoundCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728899"
---
# <a name="boundca-function"></a><span data-ttu-id="dc572-102">Funktionen BoundCA</span><span class="sxs-lookup"><span data-stu-id="dc572-102">BoundCA function</span></span>

<span data-ttu-id="dc572-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc572-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc572-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc572-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc572-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="dc572-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="dc572-106">Modifieraren `CA` anger att alla åtgärder i matrisen är adjointable och kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="dc572-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="dc572-107">Indata</span><span class="sxs-lookup"><span data-stu-id="dc572-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="dc572-108">åtgärder: t => [enhet](xref:microsoft.quantum.lang-ref.unit) , just + CTL []</span><span class="sxs-lookup"><span data-stu-id="dc572-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="dc572-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="dc572-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="dc572-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="dc572-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="dc572-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="dc572-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc572-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="dc572-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc572-113">Inte</span><span class="sxs-lookup"><span data-stu-id="dc572-113">'T</span></span>

<span data-ttu-id="dc572-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="dc572-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc572-115">Se även</span><span class="sxs-lookup"><span data-stu-id="dc572-115">See Also</span></span>

- [<span data-ttu-id="dc572-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="dc572-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)