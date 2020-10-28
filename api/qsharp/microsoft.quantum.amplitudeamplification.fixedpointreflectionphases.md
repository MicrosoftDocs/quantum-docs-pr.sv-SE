---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Funktionen FixedPointReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731995"
---
# <a name="fixedpointreflectionphases-function"></a>Funktionen FixedPointReflectionPhases

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


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