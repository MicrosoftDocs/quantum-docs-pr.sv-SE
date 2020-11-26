---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196114"
---
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Verifierar en viss sekventiell klassificerare mot en viss uppsättning förmärkta exempel.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Indata

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Den sekventiella modell som ska verifieras.


### <a name="samples--labeledsample"></a>exempel: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

De exempel som ska användas för att validera den aktuella modellen.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Den ungefärliga tolerans som ska användas i kodning av varje exempel som indatamängden för den sekventiella klassificeraren.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mått som ska användas för att klassificera varje exempel.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Schemat med vilket exempel ska ritas från validerings uppsättningen.



## <a name="output--validationresults"></a>Utdata: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Resultatet av den aktuella verifieringen.