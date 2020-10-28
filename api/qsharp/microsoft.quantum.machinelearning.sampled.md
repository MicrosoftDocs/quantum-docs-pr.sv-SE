---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Exempel funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732318"
---
# <a name="sampled-function"></a>Exempel funktion

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Exempel på en specifik matris med det aktuella schemat.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="schedule--samplingschedule"></a>schema: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Ett schema som ska användas i samplings värden.


### <a name="values--t"></a>värden: ' inte []

En matris med värden som ska samplas.



## <a name="output--t"></a>Utdata: ' t []

En matris med element från värden, efter det aktuella schemat.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

