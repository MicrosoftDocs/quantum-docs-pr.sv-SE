---
uid: Microsoft.Quantum.Arrays.ForEach
title: Förställnings åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848588"
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