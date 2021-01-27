---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fördröjd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: e53279bd3ddc5fa8bc0c862f998b273a9e17a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840605"
---
# <a name="delayeda-function"></a><span data-ttu-id="eb5fb-102">Fördröjd funktion</span><span class="sxs-lookup"><span data-stu-id="eb5fb-102">DelayedA function</span></span>

<span data-ttu-id="eb5fb-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb5fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb5fb-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb5fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb5fb-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="eb5fb-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="eb5fb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb5fb-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="eb5fb-107">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="eb5fb-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eb5fb-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="eb5fb-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="eb5fb-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="eb5fb-109">arg : 'T</span></span>

<span data-ttu-id="eb5fb-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="eb5fb-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="eb5fb-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="eb5fb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eb5fb-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="eb5fb-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eb5fb-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="eb5fb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb5fb-114">Inte</span><span class="sxs-lookup"><span data-stu-id="eb5fb-114">'T</span></span>

<span data-ttu-id="eb5fb-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="eb5fb-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb5fb-116">Se även</span><span class="sxs-lookup"><span data-stu-id="eb5fb-116">See Also</span></span>

- [<span data-ttu-id="eb5fb-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="eb5fb-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="eb5fb-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="eb5fb-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)