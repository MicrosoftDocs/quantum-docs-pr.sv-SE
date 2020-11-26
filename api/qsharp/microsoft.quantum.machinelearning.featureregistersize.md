---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196420"
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