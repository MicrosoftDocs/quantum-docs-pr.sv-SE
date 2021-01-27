---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Funktionen InferredLabels
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848398"
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