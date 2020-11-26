---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Unzippad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219965"
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

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zipinmatningsenhet](xref:Microsoft.Quantum.Arrays.Zipped)