---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Funktionen UncurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204648"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="4d888-102">Funktionen UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="4d888-102">UncurriedOp function</span></span>

<span data-ttu-id="4d888-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4d888-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4d888-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d888-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d888-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="4d888-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="4d888-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4d888-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="4d888-107">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d888-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4d888-108">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4d888-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="4d888-109">Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d888-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4d888-110">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="4d888-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4d888-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4d888-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4d888-112">Inte</span><span class="sxs-lookup"><span data-stu-id="4d888-112">'T</span></span>

<span data-ttu-id="4d888-113">Typen för den första indatamängden till en Curried-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4d888-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="4d888-114">' U</span><span class="sxs-lookup"><span data-stu-id="4d888-114">'U</span></span>

<span data-ttu-id="4d888-115">Typen för den andra ingången till en Curried-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4d888-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d888-116">Se även</span><span class="sxs-lookup"><span data-stu-id="4d888-116">See Also</span></span>

- [<span data-ttu-id="4d888-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="4d888-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="4d888-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="4d888-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="4d888-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="4d888-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)