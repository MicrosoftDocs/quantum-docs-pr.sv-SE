---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729934"
---
# <a name="windows-function"></a><span data-ttu-id="95af8-102">Windows-funktion</span><span class="sxs-lookup"><span data-stu-id="95af8-102">Windows function</span></span>

<span data-ttu-id="95af8-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95af8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95af8-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95af8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95af8-105">Returnerar alla efterföljande under matriser med längd `size` .</span><span class="sxs-lookup"><span data-stu-id="95af8-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="95af8-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="95af8-106">Description</span></span>

<span data-ttu-id="95af8-107">Den här funktionen returnerar alla `n - size + 1` undermatriser `size` i ordning, där `n` är längden på `arr` .</span><span class="sxs-lookup"><span data-stu-id="95af8-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="95af8-108">De första undermatriserna är `arr[0..size - 1], arr[1..size], arr[2..size + 1]` till och med den sista under matrisen `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="95af8-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="95af8-109">Om `size <= 0` eller `size > n` , returneras en tom matris.</span><span class="sxs-lookup"><span data-stu-id="95af8-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="95af8-110">Indata</span><span class="sxs-lookup"><span data-stu-id="95af8-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="95af8-111">Storlek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95af8-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95af8-112">Längden på undermatriserna.</span><span class="sxs-lookup"><span data-stu-id="95af8-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="95af8-113">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="95af8-113">array : 'T[]</span></span>

<span data-ttu-id="95af8-114">En matris med element.</span><span class="sxs-lookup"><span data-stu-id="95af8-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="95af8-115">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="95af8-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95af8-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="95af8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95af8-117">Inte</span><span class="sxs-lookup"><span data-stu-id="95af8-117">'T</span></span>

<span data-ttu-id="95af8-118">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="95af8-118">The type of `array` elements.</span></span>