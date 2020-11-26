---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Funktionen IntAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224351"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="a57f3-102">Funktionen IntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="a57f3-102">IntAsBoolArray function</span></span>

<span data-ttu-id="a57f3-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a57f3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a57f3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a57f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a57f3-105">Genererar en binär representation av ett positivt heltal med hjälp av en liten endian-representation för den returnerade matrisen.</span><span class="sxs-lookup"><span data-stu-id="a57f3-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="a57f3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a57f3-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="a57f3-107">Number: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a57f3-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a57f3-108">Ett positivt heltal som ska konverteras till en matris med booleska värden.</span><span class="sxs-lookup"><span data-stu-id="a57f3-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="a57f3-109">bitar: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a57f3-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a57f3-110">Antalet bitar i den binära representationen av `number` .</span><span class="sxs-lookup"><span data-stu-id="a57f3-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a57f3-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a57f3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a57f3-112">En matris med booleska värden som representerar `number` .</span><span class="sxs-lookup"><span data-stu-id="a57f3-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a57f3-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a57f3-113">Remarks</span></span>

<span data-ttu-id="a57f3-114">Inmatade värden `bits` måste vara mellan 0 och 63.</span><span class="sxs-lookup"><span data-stu-id="a57f3-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="a57f3-115">Inmatade värden `number` måste vara mellan 0 och $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="a57f3-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>