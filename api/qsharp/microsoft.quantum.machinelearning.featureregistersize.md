---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732811"
---
# <a name="featureregistersize-function"></a>Funktionen FeatureRegisterSize

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Returnerar antalet qubits som krävs för att koda en viss funktions vektor.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Indata

### <a name="sample--double"></a>exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]

En exempel funktions vektor som ska kodas till ett qubit-register.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Storleken som krävs för att koda `sample` till ett qubit-register, uttryckt som ett antal qubits.