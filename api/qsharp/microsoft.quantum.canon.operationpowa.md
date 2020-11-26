---
uid: Microsoft.Quantum.Canon.OperationPowA
title: Funktionen OperationPowA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205787"
---
# <a name="operationpowa-function"></a><span data-ttu-id="0b59d-102">Funktionen OperationPowA</span><span class="sxs-lookup"><span data-stu-id="0b59d-102">OperationPowA function</span></span>

<span data-ttu-id="0b59d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b59d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b59d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b59d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b59d-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="0b59d-105">Raises an operation to a power.</span></span>
<span data-ttu-id="0b59d-106">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="0b59d-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="0b59d-107">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="0b59d-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="0b59d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="0b59d-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="0b59d-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="0b59d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0b59d-110">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="0b59d-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0b59d-111">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b59d-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b59d-112">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="0b59d-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="0b59d-113">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="0b59d-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0b59d-114">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="0b59d-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b59d-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0b59d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b59d-116">Inte</span><span class="sxs-lookup"><span data-stu-id="0b59d-116">'T</span></span>

<span data-ttu-id="0b59d-117">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="0b59d-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b59d-118">Se även</span><span class="sxs-lookup"><span data-stu-id="0b59d-118">See Also</span></span>

- [<span data-ttu-id="0b59d-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="0b59d-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)