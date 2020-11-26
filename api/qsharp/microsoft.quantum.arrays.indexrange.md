---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Funktionen IndexRange
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220951"
---
# <a name="indexrange-function"></a>Funktionen IndexRange

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Med den här matrisen returneras ett intervall över indexets index, vilket är lämpligt för användning i en for-slinga.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Indata

### <a name="array--telement"></a>matris: ' TEleation []

En matris som en serie index ska returneras för.



## <a name="output--range"></a>Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)

Ett intervall över alla index i matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="telement"></a>"Teleteleering"

Typ av element i matrisen.