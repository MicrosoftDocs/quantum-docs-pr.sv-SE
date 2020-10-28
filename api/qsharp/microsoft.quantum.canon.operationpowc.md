---
uid: Microsoft.Quantum.Canon.OperationPowC
title: Funktionen OperationPowC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728494"
---
# <a name="operationpowc-function"></a><span data-ttu-id="f4575-102">Funktionen OperationPowC</span><span class="sxs-lookup"><span data-stu-id="f4575-102">OperationPowC function</span></span>

<span data-ttu-id="f4575-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4575-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4575-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4575-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4575-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="f4575-105">Raises an operation to a power.</span></span>
<span data-ttu-id="f4575-106">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="f4575-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="f4575-107">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="f4575-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f4575-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f4575-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="f4575-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f4575-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f4575-110">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="f4575-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f4575-111">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4575-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4575-112">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="f4575-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="f4575-113">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f4575-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f4575-114">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="f4575-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4575-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f4575-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4575-116">Inte</span><span class="sxs-lookup"><span data-stu-id="f4575-116">'T</span></span>

<span data-ttu-id="f4575-117">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="f4575-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4575-118">Se även</span><span class="sxs-lookup"><span data-stu-id="f4575-118">See Also</span></span>

- [<span data-ttu-id="f4575-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="f4575-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)