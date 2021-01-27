---
uid: Microsoft.Quantum.Arrays.Subarray
title: Under mat ris funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845421"
---
# <a name="subarray-function"></a>Under mat ris funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tar en matris och en lista med platser och skapar en ny matris som är utformad från elementen i den ursprungliga matrisen som matchar de tilldelade platserna.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="indices--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)[]

En lista med heltal som används för att definiera undermatrisen.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--t"></a>Utdata: ' t []

En matris `out` med element vars index motsvarar undermatrisen, t `out[idx] == array[indices[idx]]` . ex..

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en lista över platser som `Int[]` definierar undermatrisen.
Undermatrisens konstruktion är en baserad på att skapa en ny, djupgående kopia av den aktuella matrisen i stället för att behålla referenser.

Om `Length(indices) < Length(array)` den här funktionen kommer att returnera en delmängd av `array` . Å andra sidan `indices` upprepas motsvarande element i även om de innehåller upprepade element `array` .
Om `indices` och `array` har samma längd tillhandahåller den här funktionen permutationer av `array` .