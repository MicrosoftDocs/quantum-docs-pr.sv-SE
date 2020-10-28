---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Funktionen InferredLabels
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732350"
---
# <a name="inferredlabels-function"></a>Funktionen InferredLabels

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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