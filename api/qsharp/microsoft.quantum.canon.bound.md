---
uid: Microsoft.Quantum.Canon.Bound
title: Bound-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207606"
---
# <a name="bound-function"></a><span data-ttu-id="61ff3-102">Bound-funktion</span><span class="sxs-lookup"><span data-stu-id="61ff3-102">Bound function</span></span>

<span data-ttu-id="61ff3-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61ff3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61ff3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61ff3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61ff3-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="61ff3-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="61ff3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="61ff3-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="61ff3-107">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="61ff3-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="61ff3-108">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="61ff3-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="61ff3-109">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61ff3-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="61ff3-110">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="61ff3-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61ff3-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="61ff3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61ff3-112">Inte</span><span class="sxs-lookup"><span data-stu-id="61ff3-112">'T</span></span>

<span data-ttu-id="61ff3-113">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="61ff3-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="61ff3-114">Se även</span><span class="sxs-lookup"><span data-stu-id="61ff3-114">See Also</span></span>

- [<span data-ttu-id="61ff3-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="61ff3-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="61ff3-116">Microsoft. Quantum. Canon. Boundas</span><span class="sxs-lookup"><span data-stu-id="61ff3-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="61ff3-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="61ff3-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)