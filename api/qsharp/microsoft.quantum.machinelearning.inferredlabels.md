---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Funktionen InferredLabels
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196369"
---
# <a name="inferredlabels-function"></a>Funktionen InferredLabels

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med tanke på en klassificerings mat ris sannolikhet och en förskjutning, returnerar etiketten härledd från varje sannolikhet.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Indata

### <a name="bias--double"></a>bias: [dubbel](xref:microsoft.quantum.lang-ref.double)

Kompensationen mellan två klasser, vanligt vis resultatet av att träna en klassificerare.


### <a name="probabilities--double"></a>sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)[]

En matris med klassificerings sannolikheter för en uppsättning exempel, som vanligt vis resulterar i att klassificerings frekvensen uppskattas.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

Etiketten härleds från varje klassificerings sannolikhet.