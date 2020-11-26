---
uid: Microsoft.Quantum.Canon.BoundA
title: Bindnings funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216956"
---
# <a name="bounda-function"></a><span data-ttu-id="68773-102">Bindnings funktion</span><span class="sxs-lookup"><span data-stu-id="68773-102">BoundA function</span></span>

<span data-ttu-id="68773-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68773-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68773-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68773-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68773-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="68773-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="68773-106">Modifieraren `A` anger att alla åtgärder i matrisen är adjointable.</span><span class="sxs-lookup"><span data-stu-id="68773-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="68773-107">Indata</span><span class="sxs-lookup"><span data-stu-id="68773-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="68773-108">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just []</span><span class="sxs-lookup"><span data-stu-id="68773-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="68773-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="68773-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="68773-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="68773-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="68773-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="68773-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68773-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="68773-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68773-113">Inte</span><span class="sxs-lookup"><span data-stu-id="68773-113">'T</span></span>

<span data-ttu-id="68773-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="68773-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="68773-115">Se även</span><span class="sxs-lookup"><span data-stu-id="68773-115">See Also</span></span>

- [<span data-ttu-id="68773-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="68773-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)