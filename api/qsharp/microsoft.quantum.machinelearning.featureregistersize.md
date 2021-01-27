---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848432"
---
# <a name="featureregistersize-function"></a>Funktionen FeatureRegisterSize

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Returnerar antalet qubits som krävs för att koda en viss funktions vektor.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Indata

### <a name="sample--double"></a>exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]

En exempel funktions vektor som ska kodas till ett qubit-register.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Storleken som krävs för att koda `sample` till ett qubit-register, uttryckt som ett antal qubits.