---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: Funktionen UncurriedOpA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728293"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="d3850-102">Funktionen UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="d3850-102">UncurriedOpA function</span></span>

<span data-ttu-id="d3850-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3850-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3850-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3850-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3850-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="d3850-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="d3850-106">Modifieraren `A` anger att åtgärderna är adjointable.</span><span class="sxs-lookup"><span data-stu-id="d3850-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d3850-107">Indata</span><span class="sxs-lookup"><span data-stu-id="d3850-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="d3850-108">curriedOp: ' t-> ' U => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="d3850-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d3850-109">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d3850-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="d3850-110">Utdata: (t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="d3850-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d3850-111">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d3850-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d3850-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d3850-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3850-113">Inte</span><span class="sxs-lookup"><span data-stu-id="d3850-113">'T</span></span>

<span data-ttu-id="d3850-114">Typen för det första argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="d3850-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="d3850-115">' U</span><span class="sxs-lookup"><span data-stu-id="d3850-115">'U</span></span>

<span data-ttu-id="d3850-116">Typ av det andra argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="d3850-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3850-117">Se även</span><span class="sxs-lookup"><span data-stu-id="d3850-117">See Also</span></span>

- [<span data-ttu-id="d3850-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="d3850-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)