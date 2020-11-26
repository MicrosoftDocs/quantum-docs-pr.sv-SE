---
uid: Microsoft.Quantum.Arrays.Where
title: Där-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219931"
---
# <a name="where-function"></a><span data-ttu-id="c3088-102">Där-funktion</span><span class="sxs-lookup"><span data-stu-id="c3088-102">Where function</span></span>

<span data-ttu-id="c3088-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3088-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3088-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3088-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3088-105">Utifrån ett predikat och en matris returneras indexen för den matris där predikatet är sant.</span><span class="sxs-lookup"><span data-stu-id="c3088-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c3088-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c3088-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c3088-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3088-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3088-108">En funktion från `'T` till boolesk som används för att filtrera element.</span><span class="sxs-lookup"><span data-stu-id="c3088-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c3088-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="c3088-109">array : 'T[]</span></span>

<span data-ttu-id="c3088-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="c3088-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c3088-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c3088-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c3088-112">En matris med index där `predicate` är sant.</span><span class="sxs-lookup"><span data-stu-id="c3088-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3088-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c3088-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3088-114">Inte</span><span class="sxs-lookup"><span data-stu-id="c3088-114">'T</span></span>

<span data-ttu-id="c3088-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="c3088-115">The type of `array` elements.</span></span>