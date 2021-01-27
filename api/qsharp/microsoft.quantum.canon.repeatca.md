---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852210"
---
# <a name="repeatca-operation"></a><span data-ttu-id="84127-102">RepeatCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="84127-102">RepeatCA operation</span></span>

<span data-ttu-id="84127-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84127-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84127-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84127-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84127-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="84127-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="84127-106">Indata</span><span class="sxs-lookup"><span data-stu-id="84127-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="84127-107">OP: ' TInput => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="84127-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="84127-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="84127-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="84127-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84127-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84127-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="84127-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="84127-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="84127-111">input : 'TInput</span></span>

<span data-ttu-id="84127-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="84127-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84127-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84127-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84127-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="84127-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="84127-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="84127-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="84127-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="84127-116">Example</span></span>

<span data-ttu-id="84127-117">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="84127-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="84127-118">Se även</span><span class="sxs-lookup"><span data-stu-id="84127-118">See Also</span></span>

- [<span data-ttu-id="84127-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="84127-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="84127-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="84127-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="84127-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="84127-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="84127-122">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="84127-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)