---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funktionen för felklassificering
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732979"
---
# <a name="misclassifications-function"></a>Funktionen för felklassificering

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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