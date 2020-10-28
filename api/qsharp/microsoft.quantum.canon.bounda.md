---
uid: Microsoft.Quantum.Canon.BoundA
title: Bindnings funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728923"
---
# <a name="bounda-function"></a><span data-ttu-id="00d81-102">Bindnings funktion</span><span class="sxs-lookup"><span data-stu-id="00d81-102">BoundA function</span></span>

<span data-ttu-id="00d81-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00d81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00d81-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00d81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00d81-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="00d81-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="00d81-106">Modifieraren `A` anger att alla åtgärder i matrisen är adjointable.</span><span class="sxs-lookup"><span data-stu-id="00d81-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="00d81-107">Indata</span><span class="sxs-lookup"><span data-stu-id="00d81-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="00d81-108">åtgärder: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering []</span><span class="sxs-lookup"><span data-stu-id="00d81-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="00d81-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="00d81-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="00d81-110">Utdata: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="00d81-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="00d81-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="00d81-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00d81-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="00d81-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00d81-113">Inte</span><span class="sxs-lookup"><span data-stu-id="00d81-113">'T</span></span>

<span data-ttu-id="00d81-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="00d81-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="00d81-115">Se även</span><span class="sxs-lookup"><span data-stu-id="00d81-115">See Also</span></span>

- [<span data-ttu-id="00d81-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="00d81-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)