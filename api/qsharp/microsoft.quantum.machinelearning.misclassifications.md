---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funktionen för felklassificering
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853933"
---
# <a name="misclassifications-function"></a>Funktionen för felklassificering

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Om du har fått en uppsättning av uppskjutna etiketter och en uppsättning korrekta etiketter, returnerar index för var varje uppsättning etiketter skiljer sig.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Indata

### <a name="inferredlabels--int"></a>inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Etiketter härledda för en angiven utbildning eller validerings uppsättning.


### <a name="actuallabels--int"></a>actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

De sanna etiketterna för en angiven utbildning eller verifierings uppsättning.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris med index `idx` som `inferredLabels[idx] != actualLabels[idx]` .

## <a name="example"></a>Exempel

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```