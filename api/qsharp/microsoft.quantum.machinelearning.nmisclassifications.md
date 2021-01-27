---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Funktionen NMisclassifications
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853904"
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

## <a name="example"></a>Exempel

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```