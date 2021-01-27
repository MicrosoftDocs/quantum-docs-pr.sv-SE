---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Funktionen RotationPhasesAsReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843942"
---
# <a name="rotationphasesasreflectionphases-function"></a>Funktionen RotationPhasesAsReflectionPhases

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar faser som anges som en qubit rotation till faser som anges som partiella reflektioner.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Indata

### <a name="rotphases--rotationphases"></a>rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Matris med en qubit rotation som ska konverteras till partiella reflektioner.



## <a name="output--reflectionphases"></a>Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

En åtgärd som implementerar faser som anges som partiella reflektioner.

## <a name="references"></a>Referenser

Vi använder konventionen i

- [ *G.H. Low, i. L. Chuang,*](https://arxiv.org/abs/1707.05391) för relaterade operatorer för reflektions operatorer.