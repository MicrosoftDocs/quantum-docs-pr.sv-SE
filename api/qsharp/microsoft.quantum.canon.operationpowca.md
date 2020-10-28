---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Funktionen OperationPowCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728488"
---
# <a name="operationpowca-function"></a><span data-ttu-id="803fc-102">Funktionen OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="803fc-102">OperationPowCA function</span></span>

<span data-ttu-id="803fc-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="803fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="803fc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="803fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="803fc-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="803fc-105">Raises an operation to a power.</span></span>
<span data-ttu-id="803fc-106">Modifieraren `A` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="803fc-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="803fc-107">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="803fc-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="803fc-108">Indata</span><span class="sxs-lookup"><span data-stu-id="803fc-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="803fc-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="803fc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="803fc-110">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="803fc-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="803fc-111">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="803fc-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="803fc-112">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="803fc-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="803fc-113">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="803fc-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="803fc-114">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="803fc-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="803fc-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="803fc-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="803fc-116">Inte</span><span class="sxs-lookup"><span data-stu-id="803fc-116">'T</span></span>

<span data-ttu-id="803fc-117">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="803fc-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="803fc-118">Se även</span><span class="sxs-lookup"><span data-stu-id="803fc-118">See Also</span></span>

- [<span data-ttu-id="803fc-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="803fc-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)