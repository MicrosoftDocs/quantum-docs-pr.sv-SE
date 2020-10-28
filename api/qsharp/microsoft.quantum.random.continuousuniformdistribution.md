---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Funktionen ContinuousUniformDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725812"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="cd7eb-102">Funktionen ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="cd7eb-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="cd7eb-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cd7eb-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cd7eb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd7eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd7eb-105">Returnerar en enhetlig distribution över ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="cd7eb-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="cd7eb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cd7eb-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="cd7eb-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd7eb-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd7eb-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="cd7eb-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="cd7eb-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd7eb-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd7eb-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="cd7eb-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="cd7eb-111">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="cd7eb-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="cd7eb-112">En distribution vars slumpmässiga variates är reella tal i inklusiv-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="cd7eb-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd7eb-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cd7eb-113">Remarks</span></span>

<span data-ttu-id="cd7eb-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="cd7eb-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd7eb-115">Se även</span><span class="sxs-lookup"><span data-stu-id="cd7eb-115">See Also</span></span>

- [<span data-ttu-id="cd7eb-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="cd7eb-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)