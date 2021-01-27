---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funktionen IsSorted
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845724"
---
# <a name="issorted-function"></a>Funktionen IsSorted

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Om matrisen anges returneras en matris som definieras av en viss jämförelse funktion.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Indata

### <a name="comparison--tt---bool"></a>jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion som jämför två element som `a` anses vara mindre än eller lika med `b` om `comparison(a, b)` är `true` .


### <a name="array--t"></a>matris: ' ' []

Den matris som ska kontrol leras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om för varje par med element `a` och `b` `array` som inträffar i den ordningen, `comparison(a, b)` är `true` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `array` .

## <a name="remarks"></a>Kommentarer

Funktionen `comparison` antas vara transitiv, som IF `comparison(a, b)` och `comparison(b, c)` , sedan `comparison(a, c)` antas. Om den här egenskapen inte finns kan resultatet av den här funktionen vara felaktigt.