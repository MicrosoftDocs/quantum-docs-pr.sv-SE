---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Exempel funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211635"
---
# <a name="sampled-function"></a>Exempel funktion

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

