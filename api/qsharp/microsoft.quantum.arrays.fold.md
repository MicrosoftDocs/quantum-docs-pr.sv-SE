---
uid: Microsoft.Quantum.Arrays.Fold
title: Viknings funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848612"
---
# <a name="fold-function"></a>Viknings funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exempel

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```