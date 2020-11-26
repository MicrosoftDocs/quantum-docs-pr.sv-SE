---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: Funktionen LexographicComparison
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197592"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="a107a-102">Funktionen LexographicComparison</span><span class="sxs-lookup"><span data-stu-id="a107a-102">LexographicComparison function</span></span>

<span data-ttu-id="a107a-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a107a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a107a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a107a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a107a-105">Med en jämförelse funktion returnerar en ny funktion som lexographically jämför två matriser.</span><span class="sxs-lookup"><span data-stu-id="a107a-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="a107a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a107a-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="a107a-107">elementComparison: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a107a-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a107a-108">En funktion som jämför två element `x` och `y` returnerar om `x` är mindre än eller lika med `y` .</span><span class="sxs-lookup"><span data-stu-id="a107a-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="a107a-109">Utdata: (inte [], inte [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a107a-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a107a-110">En funktion som jämför två matriser `xs` och `ys` returnerar om `xs` inträffar före eller lika med `ys` i lexographical-ordningen.</span><span class="sxs-lookup"><span data-stu-id="a107a-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a107a-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a107a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a107a-112">Inte</span><span class="sxs-lookup"><span data-stu-id="a107a-112">'T</span></span>

<span data-ttu-id="a107a-113">Typ av element i de matriser som jämförs.</span><span class="sxs-lookup"><span data-stu-id="a107a-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="a107a-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a107a-114">Remarks</span></span>

<span data-ttu-id="a107a-115">Lexographic-jämförelsen mellan två matriser `xs` och `ys` definieras av följande procedur.</span><span class="sxs-lookup"><span data-stu-id="a107a-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="a107a-116">Vi säger att två element `x` och `y` är likvärdiga om `elementComparison(x, y)` och `elementComparison(y, x)` båda är sanna.</span><span class="sxs-lookup"><span data-stu-id="a107a-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="a107a-117">Båda matriserna jämförs element för element tills det första paret element som inte är likvärdigt.</span><span class="sxs-lookup"><span data-stu-id="a107a-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="a107a-118">Matrisen som innehåller det element som inträffar först enligt `elementComparison` inträffar först i lexographical-ordning.</span><span class="sxs-lookup"><span data-stu-id="a107a-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="a107a-119">Om inga icke-likvärdiga element hittas och en matris är längre än den andra, sägs att den kortare matrisen inträffar först.</span><span class="sxs-lookup"><span data-stu-id="a107a-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="a107a-120">Se även</span><span class="sxs-lookup"><span data-stu-id="a107a-120">See Also</span></span>

- [<span data-ttu-id="a107a-121">Microsoft. Quantum. arrayer. sorterat</span><span class="sxs-lookup"><span data-stu-id="a107a-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)