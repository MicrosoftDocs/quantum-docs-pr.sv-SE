---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Funktionen DiscreteUniformDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853725"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="cebec-102">Funktionen DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="cebec-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="cebec-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cebec-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cebec-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cebec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cebec-105">Returnerar en enhetlig distribution över ett angivet inklusivt intervall.</span><span class="sxs-lookup"><span data-stu-id="cebec-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="cebec-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cebec-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="cebec-107">min: [heltal](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cebec-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cebec-108">Det minsta heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="cebec-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="cebec-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cebec-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cebec-110">Det största heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="cebec-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="cebec-111">Utdata: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="cebec-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="cebec-112">En distribution vars slumpmässiga variates är heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="cebec-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="cebec-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="cebec-113">Example</span></span>

<span data-ttu-id="cebec-114">Följande Q #-kodfragment rullar slumpmässigt en sida med sex sidor:</span><span class="sxs-lookup"><span data-stu-id="cebec-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="cebec-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cebec-115">Remarks</span></span>

<span data-ttu-id="cebec-116">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="cebec-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cebec-117">Se även</span><span class="sxs-lookup"><span data-stu-id="cebec-117">See Also</span></span>

- [<span data-ttu-id="cebec-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="cebec-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)