---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Funktionen NMisclassifications
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725944"
---
# <a name="nmisclassifications-function"></a>Funktionen NMisclassifications

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Med en uppsättning av uppskjutna etiketter och en uppsättning korrekta etiketter, returnerar antalet index där varje uppsättning etiketter skiljer sig.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Indata

### <a name="proposed--int"></a>Föreslagen: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet index `idx` som `inferredLabels[idx] != actualLabels[idx]` .