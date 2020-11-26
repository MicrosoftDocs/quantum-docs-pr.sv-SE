---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205447"
---
# <a name="repeatc-operation"></a><span data-ttu-id="4df97-102">RepeatC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4df97-102">RepeatC operation</span></span>

<span data-ttu-id="4df97-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4df97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4df97-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4df97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4df97-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="4df97-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="4df97-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4df97-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="4df97-107">OP: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="4df97-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4df97-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="4df97-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="4df97-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4df97-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4df97-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="4df97-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="4df97-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="4df97-111">input : 'TInput</span></span>

<span data-ttu-id="4df97-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="4df97-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4df97-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4df97-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4df97-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4df97-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="4df97-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="4df97-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="4df97-116">Se även</span><span class="sxs-lookup"><span data-stu-id="4df97-116">See Also</span></span>

- [<span data-ttu-id="4df97-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="4df97-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="4df97-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="4df97-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="4df97-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="4df97-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="4df97-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="4df97-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)