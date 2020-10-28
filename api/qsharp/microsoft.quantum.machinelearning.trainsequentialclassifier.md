---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726616"
---
# <a name="trainsequentialclassifier-operation"></a>TrainSequentialClassifier-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Med hänsyn till strukturen för en sekventiell klassificerare, tågen klassificeraren på en viss etikett uppsättning.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Indata

### <a name="models--sequentialmodel"></a>modeller: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

En matris med modeller som ska användas som start punkter under träningen.


### <a name="samples--labeledsample"></a>exempel: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

En uppsättning med etiketterade utbildnings data som ska användas för att utföra utbildning.


### <a name="options--trainingoptions"></a>alternativ: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Konfiguration som ska användas vid utbildning; Se @"microsoft.quantum.machinelearning.trainingoptions" och @"microsoft.quantum.machinelearning.defaulttrainingoptions" för mer information.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Ett schema som ska användas när du väljer exempel från tränings data under utbildnings stegen.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Ett schema som ska användas när du väljer exempel från tränings data när du väljer vilken start punkt som resulterade i de bästa klassificerar poängen.



## <a name="output--sequentialmodelint"></a>Utdata: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- En Parameterisering av den aktuella klassificeraren och en förskjutning mellan de två klasserna, tillsammans motsvarar det bästa resultatet från var och en av de aktuella start punkterna.
- Antalet Cachemissar som observerats i den bästa klassificerings modellen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)