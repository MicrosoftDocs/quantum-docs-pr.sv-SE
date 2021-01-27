---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Funktionen ContinuousUniformDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842321"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="eb2ae-102">Funktionen ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="eb2ae-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="eb2ae-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="eb2ae-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="eb2ae-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="eb2ae-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="eb2ae-105">Returnerar en enhetlig distribution över ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="eb2ae-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="eb2ae-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb2ae-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="eb2ae-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb2ae-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb2ae-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="eb2ae-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="eb2ae-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb2ae-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb2ae-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="eb2ae-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="eb2ae-111">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="eb2ae-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="eb2ae-112">En distribution vars slumpmässiga variates är reella tal i inklusiv-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="eb2ae-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="eb2ae-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="eb2ae-113">Example</span></span>

<span data-ttu-id="eb2ae-114">Följande Q #-kodfragment ritar slumpmässigt en vinkel mellan $0 $ och $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="eb2ae-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="eb2ae-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="eb2ae-115">Remarks</span></span>

<span data-ttu-id="eb2ae-116">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="eb2ae-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb2ae-117">Se även</span><span class="sxs-lookup"><span data-stu-id="eb2ae-117">See Also</span></span>

- [<span data-ttu-id="eb2ae-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="eb2ae-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)