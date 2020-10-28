---
uid: Microsoft.Quantum.Canon.DelayedC
title: Funktionen DelayedC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728719"
---
# <a name="delayedc-function"></a><span data-ttu-id="9df9b-102">Funktionen DelayedC</span><span class="sxs-lookup"><span data-stu-id="9df9b-102">DelayedC function</span></span>

<span data-ttu-id="9df9b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9df9b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9df9b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9df9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9df9b-105">Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.</span><span class="sxs-lookup"><span data-stu-id="9df9b-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="9df9b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9df9b-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="9df9b-107">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="9df9b-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9df9b-108">En åtgärd som ska tillämpas på grund av att ett retur värde tillämpas</span><span class="sxs-lookup"><span data-stu-id="9df9b-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="9df9b-109">arg: ' t</span><span class="sxs-lookup"><span data-stu-id="9df9b-109">arg : 'T</span></span>

<span data-ttu-id="9df9b-110">De indatatyper som åtgärden `op` tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="9df9b-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="9df9b-111">Utdata: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit) , CTL</span><span class="sxs-lookup"><span data-stu-id="9df9b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9df9b-112">En ny åtgärd som gäller `op` för inmatade `arg`</span><span class="sxs-lookup"><span data-stu-id="9df9b-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9df9b-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9df9b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9df9b-114">Inte</span><span class="sxs-lookup"><span data-stu-id="9df9b-114">'T</span></span>

<span data-ttu-id="9df9b-115">Indatatypen för den åtgärd som ska fördröjas.</span><span class="sxs-lookup"><span data-stu-id="9df9b-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9df9b-116">Se även</span><span class="sxs-lookup"><span data-stu-id="9df9b-116">See Also</span></span>

- [<span data-ttu-id="9df9b-117">Microsoft. Quantum. Canon. fördröjt</span><span class="sxs-lookup"><span data-stu-id="9df9b-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="9df9b-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="9df9b-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)