---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Funktionen LookupFunction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220781"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="c0099-102">Funktionen LookupFunction</span><span class="sxs-lookup"><span data-stu-id="c0099-102">LookupFunction function</span></span>

<span data-ttu-id="c0099-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c0099-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c0099-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0099-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0099-105">Med en matris returneras en funktion som returnerar element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="c0099-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="c0099-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c0099-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c0099-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="c0099-107">array : 'T[]</span></span>

<span data-ttu-id="c0099-108">Matrisen som ska visas som en lookup-funktion.</span><span class="sxs-lookup"><span data-stu-id="c0099-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="c0099-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int) -></span><span class="sxs-lookup"><span data-stu-id="c0099-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="c0099-110">En funktion `f` som `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="c0099-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c0099-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c0099-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0099-112">Inte</span><span class="sxs-lookup"><span data-stu-id="c0099-112">'T</span></span>

<span data-ttu-id="c0099-113">Typ av element i matrisen som representeras som en lookup-funktion.</span><span class="sxs-lookup"><span data-stu-id="c0099-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0099-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c0099-114">Remarks</span></span>

<span data-ttu-id="c0099-115">Den här funktionen är främst användbar för att samar beta med funktioner och åtgärder som utför `Int -> 'T` funktioner som argument.</span><span class="sxs-lookup"><span data-stu-id="c0099-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="c0099-116">Detta är vanligt, t. ex. i Generator biblioteket, där Functions används för att undvika att behöva registrera en hel matris i minnet.</span><span class="sxs-lookup"><span data-stu-id="c0099-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>