---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: Funktionen UncurriedOpA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204631"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="1a30a-102">Funktionen UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="1a30a-102">UncurriedOpA function</span></span>

<span data-ttu-id="1a30a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1a30a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1a30a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a30a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a30a-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="1a30a-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="1a30a-106">Modifieraren `A` anger att åtgärderna är adjointable.</span><span class="sxs-lookup"><span data-stu-id="1a30a-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="1a30a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="1a30a-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="1a30a-108">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="1a30a-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1a30a-109">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1a30a-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="1a30a-110">Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="1a30a-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1a30a-111">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="1a30a-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1a30a-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1a30a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a30a-113">Inte</span><span class="sxs-lookup"><span data-stu-id="1a30a-113">'T</span></span>

<span data-ttu-id="1a30a-114">Typen för det första argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="1a30a-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="1a30a-115">' U</span><span class="sxs-lookup"><span data-stu-id="1a30a-115">'U</span></span>

<span data-ttu-id="1a30a-116">Typ av det andra argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="1a30a-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a30a-117">Se även</span><span class="sxs-lookup"><span data-stu-id="1a30a-117">See Also</span></span>

- [<span data-ttu-id="1a30a-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="1a30a-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)