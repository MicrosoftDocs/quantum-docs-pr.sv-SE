---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842197"
---
# <a name="windows-function"></a><span data-ttu-id="1cd14-102">Windows-funktion</span><span class="sxs-lookup"><span data-stu-id="1cd14-102">Windows function</span></span>

<span data-ttu-id="1cd14-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1cd14-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1cd14-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cd14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cd14-105">Returnerar alla efterföljande under matriser med längd `size` .</span><span class="sxs-lookup"><span data-stu-id="1cd14-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="1cd14-106">Description</span><span class="sxs-lookup"><span data-stu-id="1cd14-106">Description</span></span>

<span data-ttu-id="1cd14-107">Den här funktionen returnerar alla `n - size + 1` undermatriser `size` i ordning, där `n` är längden på `arr` .</span><span class="sxs-lookup"><span data-stu-id="1cd14-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="1cd14-108">De första undermatriserna är `arr[0..size - 1], arr[1..size], arr[2..size + 1]` till och med den sista under matrisen `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="1cd14-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="1cd14-109">Om `size <= 0` eller `size > n` , returneras en tom matris.</span><span class="sxs-lookup"><span data-stu-id="1cd14-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="1cd14-110">Indata</span><span class="sxs-lookup"><span data-stu-id="1cd14-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="1cd14-111">Storlek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1cd14-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1cd14-112">Längden på undermatriserna.</span><span class="sxs-lookup"><span data-stu-id="1cd14-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="1cd14-113">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="1cd14-113">array : 'T[]</span></span>

<span data-ttu-id="1cd14-114">En matris med element.</span><span class="sxs-lookup"><span data-stu-id="1cd14-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="1cd14-115">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="1cd14-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1cd14-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1cd14-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1cd14-117">Inte</span><span class="sxs-lookup"><span data-stu-id="1cd14-117">'T</span></span>

<span data-ttu-id="1cd14-118">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="1cd14-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="1cd14-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="1cd14-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```