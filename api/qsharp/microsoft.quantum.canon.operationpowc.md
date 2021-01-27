---
uid: Microsoft.Quantum.Canon.OperationPowC
title: Funktionen OperationPowC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852339"
---
# <a name="operationpowc-function"></a><span data-ttu-id="d71d7-102">Funktionen OperationPowC</span><span class="sxs-lookup"><span data-stu-id="d71d7-102">OperationPowC function</span></span>

<span data-ttu-id="d71d7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d71d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d71d7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d71d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d71d7-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="d71d7-105">Raises an operation to a power.</span></span>
<span data-ttu-id="d71d7-106">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="d71d7-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="d71d7-107">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="d71d7-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="d71d7-108">Indata</span><span class="sxs-lookup"><span data-stu-id="d71d7-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d71d7-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="d71d7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d71d7-110">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="d71d7-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="d71d7-111">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d71d7-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d71d7-112">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="d71d7-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="d71d7-113">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="d71d7-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d71d7-114">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="d71d7-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d71d7-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d71d7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d71d7-116">Inte</span><span class="sxs-lookup"><span data-stu-id="d71d7-116">'T</span></span>

<span data-ttu-id="d71d7-117">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="d71d7-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="d71d7-118">Se även</span><span class="sxs-lookup"><span data-stu-id="d71d7-118">See Also</span></span>

- [<span data-ttu-id="d71d7-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="d71d7-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)