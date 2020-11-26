---
uid: Microsoft.Quantum.Arrays.Flattened
title: Utplattad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221223"
---
# <a name="flattened-function"></a>Utplattad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En matris med matriser returnerar sammanfogningen av alla matriser.

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="arrays--t"></a>matriser: ' t [] []

Matris med matriser.



## <a name="output--t"></a>Utdata: ' t []

Sammanfogning av alla matriser.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.