---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219761"
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

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. arrayer. unzippad](xref:Microsoft.Quantum.Arrays.Unzipped)