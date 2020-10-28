---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Funktionen InferredLabel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732371"
---
# <a name="inferredlabel-function"></a>Funktionen InferredLabel

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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