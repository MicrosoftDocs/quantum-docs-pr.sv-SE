---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Funktionen IndexRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845784"
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

## <a name="example"></a>Exempel

Följande `for` slingor är likvärdiga:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```