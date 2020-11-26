---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Funktionen FixedPointReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191456"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="5964a-102">Funktionen FixedPointReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="5964a-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="5964a-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5964a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5964a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5964a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5964a-105">Beräknar delvis reflektions faser för amplitud-förstärkning med fast punkt.</span><span class="sxs-lookup"><span data-stu-id="5964a-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="5964a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5964a-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="5964a-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5964a-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5964a-108">Antal frågor till tillstånds förberedelsens Oracle.</span><span class="sxs-lookup"><span data-stu-id="5964a-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="5964a-109">Måste vara ett udda heltal.</span><span class="sxs-lookup"><span data-stu-id="5964a-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="5964a-110">successMin: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5964a-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5964a-111">Minsta möjliga sannolikhet för mål.</span><span class="sxs-lookup"><span data-stu-id="5964a-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="5964a-112">Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5964a-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5964a-113">Matris med faser som kan användas i en fast-punkt för amplituds förstärkning av Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="5964a-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="5964a-114">Referenser</span><span class="sxs-lookup"><span data-stu-id="5964a-114">References</span></span>

<span data-ttu-id="5964a-115">Vi använder faserna i "fast-Point amplitud-förstärkning med ett optimalt antal frågor"</span><span class="sxs-lookup"><span data-stu-id="5964a-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="5964a-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Se även "metod för sammansatta Quantum Gates"</span><span class="sxs-lookup"><span data-stu-id="5964a-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="5964a-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) för faser i `RotationPhases` formatet.</span><span class="sxs-lookup"><span data-stu-id="5964a-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>