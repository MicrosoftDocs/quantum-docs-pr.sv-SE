---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Funktionen UncurriedOpCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840043"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="d1c0d-102">Funktionen UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="d1c0d-102">UncurriedOpCA function</span></span>

<span data-ttu-id="d1c0d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1c0d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1c0d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1c0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1c0d-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="d1c0d-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="d1c0d-106">Modifieraren `CA` anger att åtgärderna är kontrollerbara och adjointable.</span><span class="sxs-lookup"><span data-stu-id="d1c0d-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d1c0d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="d1c0d-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="d1c0d-108">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="d1c0d-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d1c0d-109">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d1c0d-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="d1c0d-110">Utdata: (t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="d1c0d-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d1c0d-111">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d1c0d-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d1c0d-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d1c0d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1c0d-113">Inte</span><span class="sxs-lookup"><span data-stu-id="d1c0d-113">'T</span></span>

<span data-ttu-id="d1c0d-114">Typen för det första argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="d1c0d-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="d1c0d-115">' U</span><span class="sxs-lookup"><span data-stu-id="d1c0d-115">'U</span></span>

<span data-ttu-id="d1c0d-116">Typ av det andra argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="d1c0d-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1c0d-117">Se även</span><span class="sxs-lookup"><span data-stu-id="d1c0d-117">See Also</span></span>

- [<span data-ttu-id="d1c0d-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="d1c0d-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)