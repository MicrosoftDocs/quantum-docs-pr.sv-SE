---
uid: Microsoft.Quantum.Canon.BoundC
title: Funktionen BoundC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841036"
---
# <a name="boundc-function"></a><span data-ttu-id="069ce-102">Funktionen BoundC</span><span class="sxs-lookup"><span data-stu-id="069ce-102">BoundC function</span></span>

<span data-ttu-id="069ce-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="069ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="069ce-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="069ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="069ce-105">Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.</span><span class="sxs-lookup"><span data-stu-id="069ce-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="069ce-106">Modifieraren `C` anger att alla åtgärder i matrisen är kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="069ce-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="069ce-107">Indata</span><span class="sxs-lookup"><span data-stu-id="069ce-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="069ce-108">åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL []</span><span class="sxs-lookup"><span data-stu-id="069ce-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="069ce-109">En sekvens med åtgärder som ska utföras på en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="069ce-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="069ce-110">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="069ce-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="069ce-111">En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="069ce-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="069ce-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="069ce-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="069ce-113">Inte</span><span class="sxs-lookup"><span data-stu-id="069ce-113">'T</span></span>

<span data-ttu-id="069ce-114">Målet som varje åtgärd i matrisen agerar på.</span><span class="sxs-lookup"><span data-stu-id="069ce-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="069ce-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="069ce-115">Example</span></span>

<span data-ttu-id="069ce-116">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="069ce-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="069ce-117">och</span><span class="sxs-lookup"><span data-stu-id="069ce-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="069ce-118">Se även</span><span class="sxs-lookup"><span data-stu-id="069ce-118">See Also</span></span>

- [<span data-ttu-id="069ce-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="069ce-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)