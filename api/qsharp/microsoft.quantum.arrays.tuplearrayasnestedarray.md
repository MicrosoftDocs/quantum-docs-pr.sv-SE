---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: Funktionen TupleArrayAsNestedArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220084"
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

