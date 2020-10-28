---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Funktionen StandardReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731923"
---
# <a name="standardreflectionphases-function"></a>Funktionen StandardReflectionPhases

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


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