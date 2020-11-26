---
uid: Microsoft.Quantum.Canon.DelayedCA
title: Funktionen DelayedCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207026"
---
# <a name="delayedca-function"></a><span data-ttu-id="ccf04-102">Funktionen DelayedCA</span><span class="sxs-lookup"><span data-stu-id="ccf04-102">DelayedCA function</span></span>

<span data-ttu-id="ccf04-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ccf04-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ccf04-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccf04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccf04-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="ccf04-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="ccf04-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ccf04-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ccf04-107">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="ccf04-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ccf04-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="ccf04-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="ccf04-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="ccf04-109">arg : 'T</span></span>

<span data-ttu-id="ccf04-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ccf04-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="ccf04-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="ccf04-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ccf04-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="ccf04-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ccf04-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ccf04-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ccf04-114">Inte</span><span class="sxs-lookup"><span data-stu-id="ccf04-114">'T</span></span>

<span data-ttu-id="ccf04-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="ccf04-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccf04-116">Se även</span><span class="sxs-lookup"><span data-stu-id="ccf04-116">See Also</span></span>

- [<span data-ttu-id="ccf04-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="ccf04-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="ccf04-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="ccf04-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)