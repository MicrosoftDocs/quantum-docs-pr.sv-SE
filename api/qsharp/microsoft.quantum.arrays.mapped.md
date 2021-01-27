---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mappad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845675"
---
# <a name="mapped-function"></a>Mappad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på en matris och en funktion som har definierats för elementen i matrisen, returnerar en ny matris som består av de bilder som finns i den ursprungliga matrisen under funktionen.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Indata

### <a name="mapper--t---u"></a>Mapper: ' t-> ' U

En funktion från `'T` till `'U` som används för att mappa element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--u"></a>Utdata: U []

En matris `'U[]` med element som mappas av `mapper` funktionen.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.
### <a name="u"></a>' U

Resultat typen för `mapper` funktionen.

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en funktion `mapper: 'T -> 'U` kan vi mappa element i matrisen och skapa en ny matris av typen `'U[]` .