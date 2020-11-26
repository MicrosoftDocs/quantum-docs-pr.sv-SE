---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210003"
---
# <a name="drawmany-operation"></a><span data-ttu-id="aad25-102">DrawMany-åtgärd</span><span class="sxs-lookup"><span data-stu-id="aad25-102">DrawMany operation</span></span>

<span data-ttu-id="aad25-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aad25-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aad25-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aad25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aad25-105">Upprepar en åtgärd för ett angivet antal exempel, och samlar in utdata i en matris.</span><span class="sxs-lookup"><span data-stu-id="aad25-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="aad25-106">Indata</span><span class="sxs-lookup"><span data-stu-id="aad25-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="aad25-107">OP: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="aad25-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="aad25-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="aad25-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="aad25-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aad25-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aad25-110">Antal exempel som anropar `op` att samla in.</span><span class="sxs-lookup"><span data-stu-id="aad25-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="aad25-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="aad25-111">input : 'TInput</span></span>

<span data-ttu-id="aad25-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="aad25-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="aad25-113">Utdata: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="aad25-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aad25-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="aad25-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="aad25-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="aad25-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="aad25-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="aad25-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="aad25-117">Se även</span><span class="sxs-lookup"><span data-stu-id="aad25-117">See Also</span></span>

- [<span data-ttu-id="aad25-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="aad25-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)