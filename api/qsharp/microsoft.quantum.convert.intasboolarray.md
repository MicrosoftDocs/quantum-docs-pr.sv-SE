---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Funktionen IntAsBoolArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727537"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="ab7e0-102">Funktionen IntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="ab7e0-102">IntAsBoolArray function</span></span>

<span data-ttu-id="ab7e0-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ab7e0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ab7e0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab7e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab7e0-105">Genererar en binär representation av ett positivt heltal med hjälp av en liten endian-representation för den returnerade matrisen.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="ab7e0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ab7e0-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="ab7e0-107">Number: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab7e0-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab7e0-108">Ett positivt heltal som ska konverteras till en matris med booleska värden.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="ab7e0-109">bitar: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab7e0-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab7e0-110">Antalet bitar i den binära representationen av `number` .</span><span class="sxs-lookup"><span data-stu-id="ab7e0-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ab7e0-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ab7e0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ab7e0-112">En matris med booleska värden som representerar `number` .</span><span class="sxs-lookup"><span data-stu-id="ab7e0-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab7e0-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ab7e0-113">Remarks</span></span>

<span data-ttu-id="ab7e0-114">Inmatade värden `bits` måste vara mellan 0 och 63.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="ab7e0-115">Inmatade värden `number` måste vara mellan 0 och $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>