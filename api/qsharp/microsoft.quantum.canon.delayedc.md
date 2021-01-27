---
uid: Microsoft.Quantum.Canon.DelayedC
title: Funktionen DelayedC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840567"
---
# <a name="delayedc-function"></a><span data-ttu-id="61955-102">Funktionen DelayedC</span><span class="sxs-lookup"><span data-stu-id="61955-102">DelayedC function</span></span>

<span data-ttu-id="61955-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61955-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61955-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61955-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61955-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="61955-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="61955-106">Indata</span><span class="sxs-lookup"><span data-stu-id="61955-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="61955-107">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="61955-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61955-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="61955-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="61955-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="61955-109">arg : 'T</span></span>

<span data-ttu-id="61955-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="61955-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="61955-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="61955-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61955-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="61955-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61955-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="61955-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61955-114">Inte</span><span class="sxs-lookup"><span data-stu-id="61955-114">'T</span></span>

<span data-ttu-id="61955-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="61955-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="61955-116">Se även</span><span class="sxs-lookup"><span data-stu-id="61955-116">See Also</span></span>

- [<span data-ttu-id="61955-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="61955-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="61955-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="61955-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)