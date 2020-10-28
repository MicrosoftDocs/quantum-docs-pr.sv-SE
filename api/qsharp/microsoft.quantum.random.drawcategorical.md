---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730958"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="915f6-102">DrawCategorical-åtgärd</span><span class="sxs-lookup"><span data-stu-id="915f6-102">DrawCategorical operation</span></span>

<span data-ttu-id="915f6-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="915f6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="915f6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="915f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="915f6-105">Ritar ett slumpmässigt exempel från en kategoriska-distribution som anges av en lista över sannolika.</span><span class="sxs-lookup"><span data-stu-id="915f6-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="915f6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="915f6-106">Description</span></span>

<span data-ttu-id="915f6-107">Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.</span><span class="sxs-lookup"><span data-stu-id="915f6-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="915f6-108">Mat ris element som är lika med noll ignoreras och deras index returneras aldrig.</span><span class="sxs-lookup"><span data-stu-id="915f6-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="915f6-109">Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.</span><span class="sxs-lookup"><span data-stu-id="915f6-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="915f6-110">Indata</span><span class="sxs-lookup"><span data-stu-id="915f6-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="915f6-111">sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="915f6-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="915f6-112">En matris med flytt ALS siffror som är proportionella mot sannolikheten för att välja varje index.</span><span class="sxs-lookup"><span data-stu-id="915f6-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="915f6-113">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="915f6-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="915f6-114">Ett heltal $i $ med sannolikhet $ \Pr (i) = p_i/\ sum_i p_i $, där $p _i $ är $i $ th-elementet i `probs` .</span><span class="sxs-lookup"><span data-stu-id="915f6-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="915f6-115">Se även</span><span class="sxs-lookup"><span data-stu-id="915f6-115">See Also</span></span>

- [<span data-ttu-id="915f6-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="915f6-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)