---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Funktionen StandardReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843923"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="eb4b3-102">Funktionen StandardReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="eb4b3-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="eb4b3-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="eb4b3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="eb4b3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb4b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb4b3-105">Beräknar delvis reflektions faser för standard-amplitud-förstärkning.</span><span class="sxs-lookup"><span data-stu-id="eb4b3-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="eb4b3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb4b3-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="eb4b3-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb4b3-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb4b3-108">Antal amplituds förstärknings iterationer som genererar delvis reflektions faser för.</span><span class="sxs-lookup"><span data-stu-id="eb4b3-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="eb4b3-109">Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="eb4b3-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="eb4b3-110">En åtgärd som implementerar faser som anges som partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="eb4b3-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="eb4b3-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="eb4b3-111">Remarks</span></span>

<span data-ttu-id="eb4b3-112">Alla faser är $ \pi $, förutom den första reflektionen om start tillstånd och senaste reflektionen om mål status, som är $0 $.</span><span class="sxs-lookup"><span data-stu-id="eb4b3-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>