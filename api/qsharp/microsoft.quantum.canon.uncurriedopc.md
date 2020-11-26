---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Funktionen UncurriedOpC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204597"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="965de-102">Funktionen UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="965de-102">UncurriedOpC function</span></span>

<span data-ttu-id="965de-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="965de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="965de-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="965de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="965de-105">En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.</span><span class="sxs-lookup"><span data-stu-id="965de-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="965de-106">Modifieraren `C` anger att åtgärderna är kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="965de-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="965de-107">Indata</span><span class="sxs-lookup"><span data-stu-id="965de-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="965de-108">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="965de-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="965de-109">En funktion som returnerar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="965de-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="965de-110">Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="965de-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="965de-111">En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="965de-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="965de-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="965de-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="965de-113">Inte</span><span class="sxs-lookup"><span data-stu-id="965de-113">'T</span></span>

<span data-ttu-id="965de-114">Typen för det första argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="965de-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="965de-115">' U</span><span class="sxs-lookup"><span data-stu-id="965de-115">'U</span></span>

<span data-ttu-id="965de-116">Typ av det andra argumentet för en Curried-funktion.</span><span class="sxs-lookup"><span data-stu-id="965de-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="965de-117">Se även</span><span class="sxs-lookup"><span data-stu-id="965de-117">See Also</span></span>

- [<span data-ttu-id="965de-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="965de-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)