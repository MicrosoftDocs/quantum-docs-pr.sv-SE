---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196471"
---
# <a name="estimateclassificationprobability-operation"></a>EstimateClassificationProbability-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med ett exempel och en sekventiell klassificerare beräknar klassificerings sannolikheten för det exemplet genom att upprepade gånger mäta utdata från klassificeraren i det angivna exemplet.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Indata

### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Toleransen för att tillåta kodning av exemplet i en tillstånds förberedelse åtgärd.


### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Den sekventiella modell som används för att beräkna klassificerings sannolikheten för det aktuella exemplet.


### <a name="sample--double"></a>exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]

Funktions vektorn för det exempel som ska klassificeras.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mätningar som ska användas vid uppskattning av klassificerings sannolikheten.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

En uppskattning av klassificerings sannolikheten för det aktuella exemplet.