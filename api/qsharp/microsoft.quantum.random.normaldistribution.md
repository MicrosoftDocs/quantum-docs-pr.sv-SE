---
uid: Microsoft.Quantum.Random.NormalDistribution
title: Funktionen NormalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814185"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="125ee-102">Funktionen NormalDistribution</span><span class="sxs-lookup"><span data-stu-id="125ee-102">NormalDistribution function</span></span>

<span data-ttu-id="125ee-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="125ee-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="125ee-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="125ee-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="125ee-105">Returnerar en normal distribution med ett angivet medelvärde och varians.</span><span class="sxs-lookup"><span data-stu-id="125ee-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="125ee-106">Indata</span><span class="sxs-lookup"><span data-stu-id="125ee-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="125ee-107">medelvärde: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="125ee-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="125ee-108">varians: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="125ee-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="125ee-109">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="125ee-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="125ee-110">Exempel</span><span class="sxs-lookup"><span data-stu-id="125ee-110">Example</span></span>

<span data-ttu-id="125ee-111">Följande ritar 10 exempel från normal distribution med medel 2 och standard avvikelse 0,1:</span><span class="sxs-lookup"><span data-stu-id="125ee-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="125ee-112">Se även</span><span class="sxs-lookup"><span data-stu-id="125ee-112">See Also</span></span>

- [<span data-ttu-id="125ee-113">Microsoft. Quantum. Random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="125ee-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)