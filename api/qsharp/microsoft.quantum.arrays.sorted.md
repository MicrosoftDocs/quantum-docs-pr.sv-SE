---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorterad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730027"
---
# <a name="sorted-function"></a>Sorterad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Utifrån en matris returnerar elementen i den matrisen sorterad efter en specifik jämförelse funktion.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="comparison--tt---bool"></a>jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .


### <a name="array--t"></a>matris: ' ' []

Matrisen som ska sorteras.



## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `array` .

## <a name="remarks"></a>Kommentarer

Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas. Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.

Eftersom det här är en funktion är resultatet helt Determinstic, även om två element anses vara lika under `comparison` ; det vill säga när `comparison(a, b)` och `comparison(b, a)` är båda `true` .
I synnerhet är sorteringen som utförs av den här funktionen säkerställd att vara stabil, så att om två element `a` och `b` inträffar i den ordningen i `array` och betraktas som likvärdiga `comparison` , `a` visas även före `b` i utdata.

Exempel:

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```