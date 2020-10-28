---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Funktionen MappedOverRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730131"
---
# <a name="mappedoverrange-function"></a>Funktionen MappedOverRange

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Med ett intervall och en funktion som tar ett heltal som inmatat, returnerar en ny matris som består av avbildningarna av värdena i intervallet under funktionen.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Indata

### <a name="mapper--int---t"></a>Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> ' t

En funktion från `Int` till `'T` som används för att mappa intervall värden.


### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)

Ett heltals intervall.



## <a name="output--t"></a>Utdata: ' t []

En matris `'T[]` med element som mappas av `mapper` funktionen.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Resultat typen för `mapper` funktionen.

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en funktion `mapper: Int -> 'T` kan vi mappa värdena i intervallet och skapa en matris av typen `'T[]` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. mappas](xref:Microsoft.Quantum.Arrays.Mapped)