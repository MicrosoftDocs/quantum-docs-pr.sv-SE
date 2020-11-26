---
uid: Microsoft.Quantum.Canon.RepeatA
title: Upprepa åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205566"
---
# <a name="repeata-operation"></a><span data-ttu-id="05013-102">Upprepa åtgärd</span><span class="sxs-lookup"><span data-stu-id="05013-102">RepeatA operation</span></span>

<span data-ttu-id="05013-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05013-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05013-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05013-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05013-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="05013-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="05013-106">Indata</span><span class="sxs-lookup"><span data-stu-id="05013-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="05013-107">OP: ' TInput => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="05013-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="05013-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="05013-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="05013-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05013-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05013-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="05013-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="05013-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="05013-111">input : 'TInput</span></span>

<span data-ttu-id="05013-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="05013-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05013-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05013-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="05013-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="05013-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="05013-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="05013-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="05013-116">Se även</span><span class="sxs-lookup"><span data-stu-id="05013-116">See Also</span></span>

- [<span data-ttu-id="05013-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="05013-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="05013-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="05013-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="05013-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="05013-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="05013-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="05013-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)