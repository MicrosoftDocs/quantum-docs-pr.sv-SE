---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Unzippad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845368"
---
# <a name="unzipped-function"></a>Unzippad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med 2-tupler returnerar en tupel av två matriser, där varje innehåller elementen i tuppeln för den inmatade matrisen.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Indata

### <a name="arr--tu"></a>arr: (t. ex. ' U) []

En matris som innehåller 2-tupler



## <a name="output--tu"></a>Utdata: (inte [], ' U [])

Två matriser, det första som innehåller alla första element i indatavärdena, den andra som innehåller alla andra element i indatavärdena.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för det första elementet i varje tupel
### <a name="u"></a>' U

Typen för det andra elementet i varje tupel

## <a name="example"></a>Exempel

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zipinmatningsenhet](xref:Microsoft.Quantum.Arrays.Zipped)