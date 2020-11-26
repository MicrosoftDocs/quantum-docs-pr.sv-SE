---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205413"
---
# <a name="repeatca-operation"></a><span data-ttu-id="0c1bf-102">RepeatCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0c1bf-102">RepeatCA operation</span></span>

<span data-ttu-id="0c1bf-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c1bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c1bf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c1bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c1bf-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="0c1bf-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0c1bf-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0c1bf-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="0c1bf-107">OP: ' TInput => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="0c1bf-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0c1bf-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="0c1bf-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="0c1bf-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c1bf-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c1bf-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="0c1bf-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0c1bf-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="0c1bf-111">input : 'TInput</span></span>

<span data-ttu-id="0c1bf-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="0c1bf-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c1bf-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c1bf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0c1bf-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0c1bf-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0c1bf-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0c1bf-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="0c1bf-116">Se även</span><span class="sxs-lookup"><span data-stu-id="0c1bf-116">See Also</span></span>

- [<span data-ttu-id="0c1bf-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="0c1bf-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="0c1bf-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="0c1bf-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="0c1bf-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="0c1bf-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="0c1bf-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="0c1bf-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)