---
uid: Microsoft.Quantum.Arrays.Flattened
title: Utplattad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848622"
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

## <a name="example"></a>Exempel

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```