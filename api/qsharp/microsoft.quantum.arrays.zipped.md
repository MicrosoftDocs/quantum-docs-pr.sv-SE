---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845341"
---
# <a name="zipped-function"></a>Komprimerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Två matriser returnerar en ny uppsättning par, så att varje par innehåller ett element från varje ursprunglig matris.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Indata

### <a name="left--t"></a>vänster: ' ' []

En matris som innehåller värden för det första elementet i varje tupel.


### <a name="right--u"></a>höger: U []

En matris som innehåller värden för det andra elementet i varje tupel.



## <a name="output--tu"></a>Utdata: (t, U) []

En matris som innehåller par av formuläret `(left[idx], right[idx])` för var och en `idx` . Om de två matriserna inte är lika långa blir utdata så länge som det kortare indata.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av vänster mat ris element.
### <a name="u"></a>' U

Typ av höger mat ris element.

## <a name="example"></a>Exempel

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. arrayer. unzippad](xref:Microsoft.Quantum.Arrays.Unzipped)