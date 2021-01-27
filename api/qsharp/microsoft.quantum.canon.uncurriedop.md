---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Funktionen UncurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852012"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="999d8-102">Funktionen UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="999d8-102">UncurriedOp function</span></span>

<span data-ttu-id="999d8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="999d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="999d8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="999d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="999d8-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="999d8-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="999d8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="999d8-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="999d8-107">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999d8-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="999d8-108">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="999d8-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="999d8-109">Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999d8-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="999d8-110">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="999d8-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="999d8-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="999d8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="999d8-112">Inte</span><span class="sxs-lookup"><span data-stu-id="999d8-112">'T</span></span>

<span data-ttu-id="999d8-113">Typen för den första indatamängden till en Curried-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="999d8-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="999d8-114">' U</span><span class="sxs-lookup"><span data-stu-id="999d8-114">'U</span></span>

<span data-ttu-id="999d8-115">Typen för den andra ingången till en Curried-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="999d8-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="999d8-116">Se även</span><span class="sxs-lookup"><span data-stu-id="999d8-116">See Also</span></span>

- [<span data-ttu-id="999d8-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="999d8-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="999d8-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="999d8-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="999d8-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="999d8-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)