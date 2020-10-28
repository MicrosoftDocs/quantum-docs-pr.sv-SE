---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funktionen IsPermutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730174"
---
# <a name="ispermutation-function"></a><span data-ttu-id="c18ff-102">Funktionen IsPermutation</span><span class="sxs-lookup"><span data-stu-id="c18ff-102">IsPermutation function</span></span>

<span data-ttu-id="c18ff-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c18ff-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c18ff-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c18ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c18ff-105">Utdata är true om och bara om en specifik matris representerar en permutation.</span><span class="sxs-lookup"><span data-stu-id="c18ff-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c18ff-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c18ff-106">Description</span></span>

<span data-ttu-id="c18ff-107">`array`Med en längd mat ris `n` returneras TRUE om och endast om varje heltal från `0` ska `n - 1` visas exakt en gång i `array` , som `array` kan tolkas som en permutation i `n` element.</span><span class="sxs-lookup"><span data-stu-id="c18ff-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="c18ff-108">Indata</span><span class="sxs-lookup"><span data-stu-id="c18ff-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="c18ff-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c18ff-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c18ff-110">En matris som kan vara en permutation eller inte.</span><span class="sxs-lookup"><span data-stu-id="c18ff-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c18ff-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c18ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="c18ff-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c18ff-112">Remarks</span></span>

<span data-ttu-id="c18ff-113">En matris med längden noll är ett enkelt permutations värde.</span><span class="sxs-lookup"><span data-stu-id="c18ff-113">An array of length zero is trivially a permutation.</span></span>