---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Funktionen FixedPointReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845844"
---
# <a name="fixedpointreflectionphases-function"></a>Funktionen FixedPointReflectionPhases

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar delvis reflektions faser för amplitud-förstärkning med fast punkt.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Indata

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Antal frågor till tillstånds förberedelsens Oracle. Måste vara ett udda heltal.


### <a name="successmin--double"></a>successMin: [dubbel](xref:microsoft.quantum.lang-ref.double)

Minsta möjliga sannolikhet för mål.



## <a name="output--reflectionphases"></a>Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Matris med faser som kan användas i en fast-punkt för amplituds förstärkning av Quantum-algoritmer.

## <a name="references"></a>Referenser

Vi använder faserna i "fast-Point amplitud-förstärkning med ett optimalt antal frågor"

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Se även "metod för sammansatta Quantum Gates"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) för faser i `RotationPhases` formatet.