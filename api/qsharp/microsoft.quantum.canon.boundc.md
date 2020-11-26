---
uid: Microsoft.Quantum.Canon.BoundC
title: Funktionen BoundC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207589"
---
# <a name="boundc-function"></a><span data-ttu-id="4b6e8-102">Funktionen BoundC</span><span class="sxs-lookup"><span data-stu-id="4b6e8-102">BoundC function</span></span>

<span data-ttu-id="4b6e8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b6e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b6e8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b6e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b6e8-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="4b6e8-106">Modifieraren `C` anger att alla åtgärder i matrisen är kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4b6e8-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4b6e8-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="4b6e8-108">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL []</span><span class="sxs-lookup"><span data-stu-id="4b6e8-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="4b6e8-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="4b6e8-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="4b6e8-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4b6e8-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4b6e8-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4b6e8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b6e8-113">Inte</span><span class="sxs-lookup"><span data-stu-id="4b6e8-113">'T</span></span>

<span data-ttu-id="4b6e8-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b6e8-115">Se även</span><span class="sxs-lookup"><span data-stu-id="4b6e8-115">See Also</span></span>

- [<span data-ttu-id="4b6e8-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="4b6e8-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)