---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731067"
---
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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