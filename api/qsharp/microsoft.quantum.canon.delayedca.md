---
uid: Microsoft.Quantum.Canon.DelayedCA
title: Funktionen DelayedCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728722"
---
# <a name="delayedca-function"></a><span data-ttu-id="ac391-102">Funktionen DelayedCA</span><span class="sxs-lookup"><span data-stu-id="ac391-102">DelayedCA function</span></span>

<span data-ttu-id="ac391-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac391-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac391-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac391-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac391-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="ac391-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="ac391-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ac391-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="ac391-107">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="ac391-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="ac391-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="ac391-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="ac391-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="ac391-109">arg : 'T</span></span>

<span data-ttu-id="ac391-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ac391-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="ac391-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="ac391-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="ac391-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="ac391-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac391-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ac391-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac391-114">Inte</span><span class="sxs-lookup"><span data-stu-id="ac391-114">'T</span></span>

<span data-ttu-id="ac391-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="ac391-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac391-116">Se även</span><span class="sxs-lookup"><span data-stu-id="ac391-116">See Also</span></span>

- [<span data-ttu-id="ac391-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="ac391-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="ac391-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="ac391-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)