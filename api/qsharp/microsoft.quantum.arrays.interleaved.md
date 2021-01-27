---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Överlagrad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848119"
---
# <a name="interleaved-function"></a><span data-ttu-id="032a0-102">Överlagrad funktion</span><span class="sxs-lookup"><span data-stu-id="032a0-102">Interleaved function</span></span>

<span data-ttu-id="032a0-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="032a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="032a0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="032a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="032a0-105">Överlåter två matriser av (nästan) samma storlek.</span><span class="sxs-lookup"><span data-stu-id="032a0-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="032a0-106">Description</span><span class="sxs-lookup"><span data-stu-id="032a0-106">Description</span></span>

<span data-ttu-id="032a0-107">Den här funktionen returnerar Interfoliering av två matriser, som börjar med det första elementet från den första matrisen, sedan det första elementet från den andra matrisen och så vidare.</span><span class="sxs-lookup"><span data-stu-id="032a0-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="032a0-108">Den första matrisen måste antingen vara av samma längd som den andra, eller ha ett annat element.</span><span class="sxs-lookup"><span data-stu-id="032a0-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="032a0-109">Indata</span><span class="sxs-lookup"><span data-stu-id="032a0-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="032a0-110">första: ' ' []</span><span class="sxs-lookup"><span data-stu-id="032a0-110">first : 'T[]</span></span>

<span data-ttu-id="032a0-111">Den första matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="032a0-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="032a0-112">sekund: ' t []</span><span class="sxs-lookup"><span data-stu-id="032a0-112">second : 'T[]</span></span>

<span data-ttu-id="032a0-113">Den andra matrisen som ska överlåtas.</span><span class="sxs-lookup"><span data-stu-id="032a0-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="032a0-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="032a0-114">Output : 'T[]</span></span>

<span data-ttu-id="032a0-115">Överlagrad matris</span><span class="sxs-lookup"><span data-stu-id="032a0-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="032a0-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="032a0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="032a0-117">Inte</span><span class="sxs-lookup"><span data-stu-id="032a0-117">'T</span></span>

<span data-ttu-id="032a0-118">Typen för varje element i `first` och `second` .</span><span class="sxs-lookup"><span data-stu-id="032a0-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="032a0-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="032a0-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```