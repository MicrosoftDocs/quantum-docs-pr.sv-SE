---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Funktionen LookupFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730150"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="b2fbe-102">Funktionen LookupFunction</span><span class="sxs-lookup"><span data-stu-id="b2fbe-102">LookupFunction function</span></span>

<span data-ttu-id="b2fbe-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b2fbe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b2fbe-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2fbe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2fbe-105">Med en matris returneras en funktion som returnerar element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="b2fbe-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b2fbe-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b2fbe-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="b2fbe-107">array : 'T[]</span></span>

<span data-ttu-id="b2fbe-108">Matrisen som ska visas som en lookup-funktion.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="b2fbe-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int) -></span><span class="sxs-lookup"><span data-stu-id="b2fbe-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="b2fbe-110">En funktion `f` som `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="b2fbe-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b2fbe-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b2fbe-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2fbe-112">Inte</span><span class="sxs-lookup"><span data-stu-id="b2fbe-112">'T</span></span>

<span data-ttu-id="b2fbe-113">Typ av element i matrisen som representeras som en lookup-funktion.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2fbe-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b2fbe-114">Remarks</span></span>

<span data-ttu-id="b2fbe-115">Den här funktionen är främst användbar för att samar beta med funktioner och åtgärder som utför `Int -> 'T` funktioner som argument.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="b2fbe-116">Detta är vanligt, t. ex. i Generator biblioteket, där Functions används för att undvika att behöva registrera en hel matris i minnet.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>