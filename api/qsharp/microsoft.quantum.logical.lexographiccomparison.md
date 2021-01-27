---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: Funktionen LexographicComparison
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814384"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="c32d9-102">Funktionen LexographicComparison</span><span class="sxs-lookup"><span data-stu-id="c32d9-102">LexographicComparison function</span></span>

<span data-ttu-id="c32d9-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c32d9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c32d9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c32d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c32d9-105">Med en jämförelse funktion returnerar en ny funktion som lexographically jämför två matriser.</span><span class="sxs-lookup"><span data-stu-id="c32d9-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="c32d9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c32d9-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="c32d9-107">elementComparison: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c32d9-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c32d9-108">En funktion som jämför två element `x` och `y` returnerar om `x` är mindre än eller lika med `y` .</span><span class="sxs-lookup"><span data-stu-id="c32d9-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="c32d9-109">Utdata: (inte [], inte [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c32d9-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c32d9-110">En funktion som jämför två matriser `xs` och `ys` returnerar om `xs` inträffar före eller lika med `ys` i lexographical-ordningen.</span><span class="sxs-lookup"><span data-stu-id="c32d9-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c32d9-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c32d9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c32d9-112">Inte</span><span class="sxs-lookup"><span data-stu-id="c32d9-112">'T</span></span>

<span data-ttu-id="c32d9-113">Typ av element i de matriser som jämförs.</span><span class="sxs-lookup"><span data-stu-id="c32d9-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="c32d9-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c32d9-114">Remarks</span></span>

<span data-ttu-id="c32d9-115">Lexographic-jämförelsen mellan två matriser `xs` och `ys` definieras av följande procedur.</span><span class="sxs-lookup"><span data-stu-id="c32d9-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="c32d9-116">Vi säger att två element `x` och `y` är likvärdiga om `elementComparison(x, y)` och `elementComparison(y, x)` båda är sanna.</span><span class="sxs-lookup"><span data-stu-id="c32d9-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="c32d9-117">Båda matriserna jämförs element för element tills det första paret element som inte är likvärdigt.</span><span class="sxs-lookup"><span data-stu-id="c32d9-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="c32d9-118">Matrisen som innehåller det element som inträffar först enligt `elementComparison` inträffar först i lexographical-ordning.</span><span class="sxs-lookup"><span data-stu-id="c32d9-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="c32d9-119">Om inga icke-likvärdiga element hittas och en matris är längre än den andra, sägs att den kortare matrisen inträffar först.</span><span class="sxs-lookup"><span data-stu-id="c32d9-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="c32d9-120">Se även</span><span class="sxs-lookup"><span data-stu-id="c32d9-120">See Also</span></span>

- [<span data-ttu-id="c32d9-121">Microsoft. Quantum. arrayer. sorterat</span><span class="sxs-lookup"><span data-stu-id="c32d9-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)