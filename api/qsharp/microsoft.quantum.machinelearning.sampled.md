---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Exempel funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854953"
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

