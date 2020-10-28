---
uid: Microsoft.Quantum.Canon.RepeatA
title: Upprepa åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728440"
---
# <a name="repeata-operation"></a><span data-ttu-id="f4e43-102">Upprepa åtgärd</span><span class="sxs-lookup"><span data-stu-id="f4e43-102">RepeatA operation</span></span>

<span data-ttu-id="f4e43-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4e43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4e43-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4e43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4e43-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="f4e43-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="f4e43-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f4e43-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="f4e43-107">OP: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) just</span><span class="sxs-lookup"><span data-stu-id="f4e43-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f4e43-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="f4e43-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f4e43-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4e43-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4e43-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="f4e43-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f4e43-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="f4e43-111">input : 'TInput</span></span>

<span data-ttu-id="f4e43-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="f4e43-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4e43-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4e43-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4e43-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f4e43-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f4e43-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f4e43-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="f4e43-116">Se även</span><span class="sxs-lookup"><span data-stu-id="f4e43-116">See Also</span></span>

- [<span data-ttu-id="f4e43-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="f4e43-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f4e43-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="f4e43-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f4e43-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="f4e43-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="f4e43-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f4e43-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)