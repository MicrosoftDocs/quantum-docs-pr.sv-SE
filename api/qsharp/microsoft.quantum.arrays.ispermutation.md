---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funktionen IsPermutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848097"
---
# <a name="ispermutation-function"></a><span data-ttu-id="cd639-102">Funktionen IsPermutation</span><span class="sxs-lookup"><span data-stu-id="cd639-102">IsPermutation function</span></span>

<span data-ttu-id="cd639-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cd639-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cd639-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd639-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd639-105">Utdata är true om och bara om en specifik matris representerar en permutation.</span><span class="sxs-lookup"><span data-stu-id="cd639-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="cd639-106">Description</span><span class="sxs-lookup"><span data-stu-id="cd639-106">Description</span></span>

<span data-ttu-id="cd639-107">`array`Med en längd mat ris `n` returneras TRUE om och endast om varje heltal från `0` ska `n - 1` visas exakt en gång i `array` , som `array` kan tolkas som en permutation i `n` element.</span><span class="sxs-lookup"><span data-stu-id="cd639-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="cd639-108">Indata</span><span class="sxs-lookup"><span data-stu-id="cd639-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="cd639-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cd639-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cd639-110">En matris som kan vara en permutation eller inte.</span><span class="sxs-lookup"><span data-stu-id="cd639-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd639-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd639-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="cd639-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="cd639-112">Example</span></span>

<span data-ttu-id="cd639-113">Följande Q #-kod skriver ut meddelandet "all diagnostik har slutförts":</span><span class="sxs-lookup"><span data-stu-id="cd639-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="cd639-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cd639-114">Remarks</span></span>

<span data-ttu-id="cd639-115">En matris med längden noll är ett enkelt permutations värde.</span><span class="sxs-lookup"><span data-stu-id="cd639-115">An array of length zero is trivially a permutation.</span></span>