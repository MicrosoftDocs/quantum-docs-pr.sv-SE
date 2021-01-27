---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Funktionen InferredLabel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848424"
---
# <a name="inferredlabel-function"></a>Funktionen InferredLabel

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med hänsyn till klassificerings sannolikhet och en förskjutning, returnerar etiketten härledd från den sannolikheten.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Indata

### <a name="bias--double"></a>bias: [dubbel](xref:microsoft.quantum.lang-ref.double)

Kompensationen mellan två klasser, vanligt vis resultatet av att träna en klassificerare.


### <a name="probability--double"></a>sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)

En klassificering som är sannolikhet för ett visst exempel, vilket vanligt vis uppstår vid uppskattning av klassificerings frekvensen.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Etiketten härleddes från den klassificerings sannolikheten.