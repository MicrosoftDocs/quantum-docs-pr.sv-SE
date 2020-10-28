---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Funktionen UncurriedOpC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728290"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="61f95-102">Funktionen UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="61f95-102">UncurriedOpC function</span></span>

<span data-ttu-id="61f95-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61f95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61f95-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61f95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61f95-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="61f95-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="61f95-106">Modifieraren `C` anger att åtgärderna är kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="61f95-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="61f95-107">Indata</span><span class="sxs-lookup"><span data-stu-id="61f95-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="61f95-108">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="61f95-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="61f95-109">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="61f95-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="61f95-110">Utdata: (t) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="61f95-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="61f95-111">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="61f95-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61f95-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="61f95-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61f95-113">Inte</span><span class="sxs-lookup"><span data-stu-id="61f95-113">'T</span></span>

<span data-ttu-id="61f95-114">Typen för det första argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="61f95-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="61f95-115">' U</span><span class="sxs-lookup"><span data-stu-id="61f95-115">'U</span></span>

<span data-ttu-id="61f95-116">Typ av det andra argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="61f95-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="61f95-117">Se även</span><span class="sxs-lookup"><span data-stu-id="61f95-117">See Also</span></span>

- [<span data-ttu-id="61f95-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="61f95-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)