---
uid: Microsoft.Quantum.Canon.OperationPow
title: Funktionen OperationPow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728530"
---
# <a name="operationpow-function"></a><span data-ttu-id="50884-102">Funktionen OperationPow</span><span class="sxs-lookup"><span data-stu-id="50884-102">OperationPow function</span></span>

<span data-ttu-id="50884-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50884-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50884-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50884-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50884-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="50884-105">Raises an operation to a power.</span></span>

<span data-ttu-id="50884-106">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="50884-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="50884-107">Indata</span><span class="sxs-lookup"><span data-stu-id="50884-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="50884-108">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50884-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50884-109">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="50884-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="50884-110">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50884-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50884-111">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="50884-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="50884-112">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50884-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50884-113">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="50884-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50884-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="50884-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50884-115">Inte</span><span class="sxs-lookup"><span data-stu-id="50884-115">'T</span></span>

<span data-ttu-id="50884-116">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="50884-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="50884-117">Se även</span><span class="sxs-lookup"><span data-stu-id="50884-117">See Also</span></span>

- [<span data-ttu-id="50884-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="50884-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="50884-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="50884-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="50884-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="50884-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)