---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Funktionen DefaultTrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855995"
---
# <a name="defaulttrainingoptions-function"></a>Funktionen DefaultTrainingOptions

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Returnerar en standard uppsättning med alternativ för utbildningar för utbildning.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Utdata: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

En rimlig uppsättning standard alternativ för utbildning som används vid utbildning av utbildning.

## <a name="example"></a>Exempel

Om du vill använda standard alternativen, men med ytterligare mått, använder du `w/` operatorn:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```