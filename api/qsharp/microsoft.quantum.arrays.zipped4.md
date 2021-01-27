---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Funktionen Zipped4
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845317"
---
# <a name="zipped4-function"></a>Funktionen Zipped4

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med fyra matriser returnerar en ny matris med 4-tupler, så att varje 4-tupel innehåller ett element från varje ursprunglig matris.

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Indata

### <a name="first--t1"></a>första: ' t 1 []

En matris som innehåller värden för det första elementet i varje tupel.


### <a name="second--t2"></a>sekund: inte 2 []

En matris som innehåller värden för det andra elementet i varje tupel.


### <a name="third--t3"></a>tredje: inte 3 []

En matris som innehåller värden för det tredje elementet i varje tupel.


### <a name="fourth--t4"></a>fjärde: inte 4 []

En matris som innehåller värden för det fjärde elementet i varje tupel.



## <a name="output--t1t2t3t4"></a>Utdata: (t. ex. 1, inte den 3, inte 4) []

En matris som innehåller 4 tupler av formuläret `(first[idx], second[idx], third[idx], fourth[idx])` för var och en `idx` . Om de fyra matriserna inte är lika långa blir utdata så länge som det kortare indata.

## <a name="type-parameters"></a>Typparametrar

### <a name="t1"></a>T 1

Typen för de första mat ris elementen.
### <a name="t2"></a>Inte 2

Typ av andra mat ris element.
### <a name="t3"></a>Inte 3

Typen för de tredje mat ris elementen.
### <a name="t4"></a>Inte 4

Typ av fjärde mat ris element.

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zipinmatningsenhet](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)