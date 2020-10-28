---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728434"
---
# <a name="repeatca-operation"></a><span data-ttu-id="c241b-102">RepeatCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c241b-102">RepeatCA operation</span></span>

<span data-ttu-id="c241b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c241b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c241b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c241b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c241b-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="c241b-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="c241b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c241b-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="c241b-107">OP: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="c241b-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c241b-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="c241b-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="c241b-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c241b-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c241b-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="c241b-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c241b-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="c241b-111">input : 'TInput</span></span>

<span data-ttu-id="c241b-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="c241b-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c241b-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c241b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c241b-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c241b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c241b-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="c241b-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="c241b-116">Se även</span><span class="sxs-lookup"><span data-stu-id="c241b-116">See Also</span></span>

- [<span data-ttu-id="c241b-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="c241b-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="c241b-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="c241b-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="c241b-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="c241b-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="c241b-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="c241b-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)