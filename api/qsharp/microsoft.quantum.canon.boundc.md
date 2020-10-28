---
uid: Microsoft.Quantum.Canon.BoundC
title: Funktionen BoundC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728914"
---
# <a name="boundc-function"></a><span data-ttu-id="189b6-102">Funktionen BoundC</span><span class="sxs-lookup"><span data-stu-id="189b6-102">BoundC function</span></span>

<span data-ttu-id="189b6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="189b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="189b6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="189b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="189b6-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="189b6-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="189b6-106">Modifieraren `C` anger att alla åtgärder i matrisen är kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="189b6-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="189b6-107">Indata</span><span class="sxs-lookup"><span data-stu-id="189b6-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="189b6-108">åtgärder: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL []</span><span class="sxs-lookup"><span data-stu-id="189b6-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="189b6-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="189b6-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="189b6-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="189b6-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="189b6-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="189b6-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="189b6-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="189b6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="189b6-113">Inte</span><span class="sxs-lookup"><span data-stu-id="189b6-113">'T</span></span>

<span data-ttu-id="189b6-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="189b6-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="189b6-115">Se även</span><span class="sxs-lookup"><span data-stu-id="189b6-115">See Also</span></span>

- [<span data-ttu-id="189b6-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="189b6-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)