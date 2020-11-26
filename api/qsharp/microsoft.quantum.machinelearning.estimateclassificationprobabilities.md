---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211907"
---
# <a name="estimateclassificationprobabilities-operation"></a>EstimateClassificationProbabilities-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med en uppsättning exempel och en sekventiell klassificerare beräknar klassificerings sannolikheten för dessa prover genom att upprepade gånger mäta utdata från klassificeraren i varje exempel.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Indata

### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Toleransen för att tillåta kodning av exemplet i en tillstånds förberedelse åtgärd.


### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Den sekventiella modell som används för att uppskatta klassificerings sannolikheten för de aktuella exemplen.


### <a name="samples--double"></a>exempel: [Double](xref:microsoft.quantum.lang-ref.double)[] []

En matris med funktions vektorer för varje exempel som ska klassificeras.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mätningar som ska användas vid uppskattning av klassificerings sannolikheten.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]

En matris med uppskattningar av klassificerings sannolikheten för varje angivet exempel.