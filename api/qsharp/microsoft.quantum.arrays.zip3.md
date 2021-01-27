---
uid: Microsoft.Quantum.Arrays.Zip3
title: Funktionen Zip3
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845359"
---
# <a name="zip3-function"></a>Funktionen Zip3

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip3 är föråldrad. Använd <xref:Microsoft.Quantum.Arrays.Zipped3> i stället.

Med tre matriser returnerar en ny matris med 3-tupler, så att varje 3-tupel innehåller ett element från varje ursprunglig matris.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Indata

### <a name="first--t1"></a>första: ' t 1 []

En matris som innehåller värden för det första elementet i varje tupel.


### <a name="second--t2"></a>sekund: inte 2 []

En matris som innehåller värden för det andra elementet i varje tupel.


### <a name="third--t3"></a>tredje: inte 3 []

En matris som innehåller värden för det tredje elementet i varje tupel.



## <a name="output--t1t2t3"></a>Utdata: (t. ex. 1, inte 2, t 3) []

En matris som innehåller 3 tupler av formuläret `(first[idx], second[idx], third[idx])` för var och en `idx` . Om de tre matriserna inte är lika långa blir utdata så länge som det kortare indata.

## <a name="type-parameters"></a>Typparametrar

### <a name="t1"></a>T 1

Typen för de första mat ris elementen.
### <a name="t2"></a>Inte 2

Typ av andra mat ris element.
### <a name="t3"></a>Inte 3

Typen för de tredje mat ris elementen.

## <a name="see-also"></a>Se även

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)