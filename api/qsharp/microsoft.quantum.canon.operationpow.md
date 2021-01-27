---
uid: Microsoft.Quantum.Canon.OperationPow
title: Funktionen OperationPow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852387"
---
# <a name="operationpow-function"></a><span data-ttu-id="f011b-102">Funktionen OperationPow</span><span class="sxs-lookup"><span data-stu-id="f011b-102">OperationPow function</span></span>

<span data-ttu-id="f011b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f011b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f011b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f011b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f011b-105">Genererar en åtgärd till en exponent.</span><span class="sxs-lookup"><span data-stu-id="f011b-105">Raises an operation to a power.</span></span>

<span data-ttu-id="f011b-106">Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.</span><span class="sxs-lookup"><span data-stu-id="f011b-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="f011b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="f011b-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f011b-108">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f011b-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f011b-109">En åtgärd $U $ som representerar den port som ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="f011b-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f011b-110">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f011b-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f011b-111">Antalet gånger som $U $ ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="f011b-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="f011b-112">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f011b-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f011b-113">En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="f011b-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f011b-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f011b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f011b-115">Inte</span><span class="sxs-lookup"><span data-stu-id="f011b-115">'T</span></span>

<span data-ttu-id="f011b-116">Typ av åtgärd som ska användas.</span><span class="sxs-lookup"><span data-stu-id="f011b-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="f011b-117">Se även</span><span class="sxs-lookup"><span data-stu-id="f011b-117">See Also</span></span>

- [<span data-ttu-id="f011b-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="f011b-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="f011b-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="f011b-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="f011b-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="f011b-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)