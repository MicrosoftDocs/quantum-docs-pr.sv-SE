---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Funktionen TransformedContinuousDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857760"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="b95dd-102">Funktionen TransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="b95dd-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="b95dd-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b95dd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b95dd-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b95dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b95dd-105">Med en kontinuerlig distribution returnerar en ny distribution som transformerar originalet med en specifik funktion.</span><span class="sxs-lookup"><span data-stu-id="b95dd-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b95dd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b95dd-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="b95dd-107">transformering: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b95dd-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b95dd-108">En funktion som transformerar variates för den ursprungliga distributionen till den transformerade distributionen.</span><span class="sxs-lookup"><span data-stu-id="b95dd-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="b95dd-109">distribution: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b95dd-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b95dd-110">Den ursprungliga fördelningen som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="b95dd-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b95dd-111">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b95dd-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b95dd-112">En ny distribution som är relaterad till `distribution` av transformeringen som erhålls av `transform` .</span><span class="sxs-lookup"><span data-stu-id="b95dd-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="b95dd-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="b95dd-113">Example</span></span>

<span data-ttu-id="b95dd-114">Följande två distributioner är identiska:</span><span class="sxs-lookup"><span data-stu-id="b95dd-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```