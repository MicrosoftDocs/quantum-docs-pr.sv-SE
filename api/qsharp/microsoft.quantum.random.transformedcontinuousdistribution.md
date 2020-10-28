---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Funktionen TransformedContinuousDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726460"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="fb59d-102">Funktionen TransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="fb59d-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="fb59d-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="fb59d-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="fb59d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb59d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb59d-105">Med en kontinuerlig distribution returnerar en ny distribution som transformerar originalet med en specifik funktion.</span><span class="sxs-lookup"><span data-stu-id="fb59d-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="fb59d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fb59d-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="fb59d-107">transformering: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb59d-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb59d-108">En funktion som transformerar variates för den ursprungliga distributionen till den transformerade distributionen.</span><span class="sxs-lookup"><span data-stu-id="fb59d-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="fb59d-109">distribution: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="fb59d-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="fb59d-110">Den ursprungliga fördelningen som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="fb59d-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="fb59d-111">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="fb59d-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="fb59d-112">En ny distribution som är relaterad till `distribution` av transformeringen som erhålls av `transform` .</span><span class="sxs-lookup"><span data-stu-id="fb59d-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>