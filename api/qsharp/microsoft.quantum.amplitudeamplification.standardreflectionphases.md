---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Funktionen StandardReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191133"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="061f2-102">Funktionen StandardReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="061f2-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="061f2-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="061f2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="061f2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="061f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="061f2-105">Beräknar delvis reflektions faser för standard-amplitud-förstärkning.</span><span class="sxs-lookup"><span data-stu-id="061f2-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="061f2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="061f2-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="061f2-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="061f2-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="061f2-108">Antal amplituds förstärknings iterationer som genererar delvis reflektions faser för.</span><span class="sxs-lookup"><span data-stu-id="061f2-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="061f2-109">Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="061f2-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="061f2-110">En åtgärd som implementerar faser som anges som partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="061f2-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="061f2-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="061f2-111">Remarks</span></span>

<span data-ttu-id="061f2-112">Alla faser är $ \pi $, förutom den första reflektionen om start tillstånd och senaste reflektionen om mål status, som är $0 $.</span><span class="sxs-lookup"><span data-stu-id="061f2-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>