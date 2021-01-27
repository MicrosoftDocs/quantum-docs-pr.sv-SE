---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844390"
---
# <a name="estimategradient-operation"></a>EstimateGradient-åtgärd

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Uppskattar inlärnings toningen för en sekventiell klassificerare i en viss modell och för en viss kodad indatamängd.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Indata

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Den sekventiella modell vars toning ska beräknas.


### <a name="encodedinput--stategenerator"></a>encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

En inläsning till den sekventiella klassificeraren, kodad i en tillstånds förberedelse åtgärd.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mått som ska användas för att uppskatta övertoningen.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]

En uppskattning av inlärnings toningen vid angivna ingångs-och modell parametrar.

## <a name="remarks"></a>Kommentarer

Den här åtgärden använder ett Hadamard-test och parameter Shift-tekniken tillsammans för att beräkna övertoningen.