---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853947"
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