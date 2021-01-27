---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: Funktionen TupleArrayAsNestedArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845399"
---
# <a name="tuplearrayasnestedarray-function"></a>Funktionen TupleArrayAsNestedArray

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förvandlar en lista med 2-tupler till en kapslad matris.

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a>Indata

### <a name="tuplelist--tt"></a>tupleList: (t) []

Lista över 2-tupler som ska omvandlas till en kapslad matris.



## <a name="output--t"></a>Utdata: ' t [] []

En kapslad matris med längd som matchar tupleList.

## <a name="example"></a>Exempel

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

