---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Funktionen MappedByIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845672"
---
# <a name="mappedbyindex-function"></a>Funktionen MappedByIndex

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på en matris och en funktion som har definierats för de indexerade elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Indata

### <a name="mapper--intt---u"></a>Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U

En funktion från `(Int, 'T)` till `'U` som används för att mappa element och deras index.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--u"></a>Utdata: U []

En matris `'U[]` med element som mappas av `mapper` funktionen.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.
### <a name="u"></a>' U

Resultat typen för `mapper` funktionen.

## <a name="example"></a>Exempel

Följande två rader är likvärdiga:

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

och

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. mappas](xref:Microsoft.Quantum.Arrays.Mapped)