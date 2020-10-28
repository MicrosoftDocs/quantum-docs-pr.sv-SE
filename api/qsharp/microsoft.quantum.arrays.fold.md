---
uid: Microsoft.Quantum.Arrays.Fold
title: Viknings funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730243"
---
# <a name="fold-function"></a>Viknings funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Itererar en funktion `f` genom en matris `array` och returnerar `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Indata

### <a name="folder--statet---state"></a>mapp: (' State, s)-> ' status

En funktion som ska vikas över matrisen.


### <a name="state--state"></a>tillstånd: status

Mappens initiala tillstånd.


### <a name="array--t"></a>matris: ' ' []

En matris med värden som ska vikas över.



## <a name="output--state"></a>Utdata: status

Det slutliga tillstånd som returneras av mappen efter att du har itererat över alla element i `array` .

## <a name="type-parameters"></a>Typparametrar

### <a name="state"></a>Status

Den typ av tillstånd `folder` som funktionen körs på, dvs accepterar som första argument och returnerar.
### <a name="t"></a>Inte

Typ av `array` element.