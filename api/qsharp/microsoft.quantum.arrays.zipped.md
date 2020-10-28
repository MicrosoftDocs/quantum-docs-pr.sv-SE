---
uid: Microsoft.Quantum.Arrays.Zipped
title: Komprimerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729910"
---
# <a name="zipped-function"></a>Komprimerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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