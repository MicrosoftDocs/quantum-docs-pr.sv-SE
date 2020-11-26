---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 02a300a2e1029d0e09aba19d090e15128fede717
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211479"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med hänsyn till strukturen för en sekventiell klassificerare, träna klassificeraren på en viss etikett uppsättning från en viss modell.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Indata

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Den sekventiella modellen som ska användas som utgångs punkt för träning.


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

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)