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
# <a name="standardreflectionphases-function"></a>Funktionen StandardReflectionPhases

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar delvis reflektions faser för standard-amplitud-förstärkning.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Indata

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Antal amplituds förstärknings iterationer som genererar delvis reflektions faser för.



## <a name="output--reflectionphases"></a>Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

En åtgärd som implementerar faser som anges som partiella reflektioner

## <a name="remarks"></a>Kommentarer

Alla faser är $ \pi $, förutom den första reflektionen om start tillstånd och senaste reflektionen om mål status, som är $0 $.