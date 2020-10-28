---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fördröjd funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728734"
---
# <a name="delayeda-function"></a><span data-ttu-id="a4abb-102">Fördröjd funktion</span><span class="sxs-lookup"><span data-stu-id="a4abb-102">DelayedA function</span></span>

<span data-ttu-id="a4abb-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a4abb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a4abb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4abb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4abb-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="a4abb-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="a4abb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a4abb-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="a4abb-107">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="a4abb-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a4abb-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="a4abb-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="a4abb-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="a4abb-109">arg : 'T</span></span>

<span data-ttu-id="a4abb-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="a4abb-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="a4abb-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="a4abb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a4abb-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="a4abb-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a4abb-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a4abb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a4abb-114">Inte</span><span class="sxs-lookup"><span data-stu-id="a4abb-114">'T</span></span>

<span data-ttu-id="a4abb-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="a4abb-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4abb-116">Se även</span><span class="sxs-lookup"><span data-stu-id="a4abb-116">See Also</span></span>

- [<span data-ttu-id="a4abb-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="a4abb-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="a4abb-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a4abb-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)