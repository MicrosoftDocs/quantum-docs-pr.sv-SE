---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840238"
---
# <a name="repeatc-operation"></a><span data-ttu-id="65117-102">RepeatC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="65117-102">RepeatC operation</span></span>

<span data-ttu-id="65117-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65117-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65117-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65117-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65117-105">Upprepar en åtgärd ett angivet antal gånger.</span><span class="sxs-lookup"><span data-stu-id="65117-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="65117-106">Indata</span><span class="sxs-lookup"><span data-stu-id="65117-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="65117-107">OP: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="65117-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="65117-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="65117-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="65117-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="65117-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="65117-110">Antalet gånger som ska anropas `op` .</span><span class="sxs-lookup"><span data-stu-id="65117-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="65117-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="65117-111">input : 'TInput</span></span>

<span data-ttu-id="65117-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="65117-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65117-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65117-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65117-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="65117-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="65117-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="65117-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="65117-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="65117-116">Example</span></span>

<span data-ttu-id="65117-117">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="65117-117">The following are equivalent:</span></span>

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="65117-118">Se även</span><span class="sxs-lookup"><span data-stu-id="65117-118">See Also</span></span>

- [<span data-ttu-id="65117-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="65117-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="65117-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="65117-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="65117-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="65117-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="65117-122">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="65117-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)