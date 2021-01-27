---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846209"
---
# <a name="drawmany-operation"></a><span data-ttu-id="32232-102">DrawMany-åtgärd</span><span class="sxs-lookup"><span data-stu-id="32232-102">DrawMany operation</span></span>

<span data-ttu-id="32232-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="32232-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="32232-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32232-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32232-105">Upprepar en åtgärd för ett angivet antal exempel, och samlar in utdata i en matris.</span><span class="sxs-lookup"><span data-stu-id="32232-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="32232-106">Indata</span><span class="sxs-lookup"><span data-stu-id="32232-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="32232-107">OP: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="32232-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="32232-108">Åtgärden som ska anropas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="32232-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="32232-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32232-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32232-110">Antal exempel som anropar `op` att samla in.</span><span class="sxs-lookup"><span data-stu-id="32232-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="32232-111">inmatade: ' TInput</span><span class="sxs-lookup"><span data-stu-id="32232-111">input : 'TInput</span></span>

<span data-ttu-id="32232-112">Inpasset som ska skickas till `op` .</span><span class="sxs-lookup"><span data-stu-id="32232-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="32232-113">Utdata: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="32232-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="32232-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="32232-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="32232-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="32232-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="32232-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="32232-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="32232-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="32232-117">Example</span></span>

<span data-ttu-id="32232-118">Följande exempel är ett heltal, med en åtgärd som samplar en enskild bit i taget.</span><span class="sxs-lookup"><span data-stu-id="32232-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="32232-119">Se även</span><span class="sxs-lookup"><span data-stu-id="32232-119">See Also</span></span>

- [<span data-ttu-id="32232-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="32232-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)