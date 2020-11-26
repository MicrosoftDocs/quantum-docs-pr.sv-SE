---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Funktionen NMisclassifications
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196318"
---
# <a name="nmisclassifications-function"></a>Funktionen NMisclassifications

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med en uppsättning av uppskjutna etiketter och en uppsättning korrekta etiketter, returnerar antalet index där varje uppsättning etiketter skiljer sig.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Indata

### <a name="proposed--int"></a>Föreslagen: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet index `idx` som `inferredLabels[idx] != actualLabels[idx]` .