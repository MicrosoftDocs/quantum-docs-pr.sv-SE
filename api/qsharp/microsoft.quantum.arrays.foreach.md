---
uid: Microsoft.Quantum.Arrays.ForEach
title: Förställnings åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221155"
---
# <a name="foreach-operation"></a>Förställnings åtgärd

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris och en åtgärd som har definierats för elementen i matrisen returnerar en ny matris som består av de avbildningar av den ursprungliga matrisen under åtgärden.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Indata

### <a name="action--t--u"></a>åtgärd: s => ' U 

En åtgärd från `'T` till `'U` som tillämpas på varje-element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--u"></a>Utdata: U []

En matris `'U[]` med element som mappas av `action` åtgärden.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.
### <a name="u"></a>' U

`action`Åtgärdens resultat typ.

## <a name="remarks"></a>Kommentarer

Åtgärden definieras för generiska typer, dvs. När vi har en matris `'T[]` och en åtgärd `action : 'T -> 'U` kan vi mappa element i matrisen och skapa en ny matris av typen `'U[]` .