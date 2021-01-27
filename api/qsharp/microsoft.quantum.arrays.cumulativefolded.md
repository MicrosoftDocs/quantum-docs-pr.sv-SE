---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Funktionen CumulativeFolded
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846218"
---
# <a name="cumulativefolded-function"></a>Funktionen CumulativeFolded

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kombinerar mappad och vikning till en enda funktion

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Description

Den här funktionen upprepar `fn` funktionen genom matrisen, med början från ett initialt tillstånd `state` och returnerar alla mellanliggande värden, inte inklusive det ursprungliga läget.

## <a name="input"></a>Indata

### <a name="fn--statet---state"></a>FN: (' State, s)-> ' status

En funktion som ska vikas över matrisen


### <a name="state--state"></a>tillstånd: status

Initialt tillstånd att vikas


### <a name="array--t"></a>matris: ' ' []

En matris med värden som ska vikas



## <a name="output--state"></a>Utdata: "State []

Alla mellanliggande tillstånd, inklusive det slutliga tillståndet, men inte det ursprungliga tillståndet.
Längden på den utgående matrisen har samma längd som `array` .

## <a name="type-parameters"></a>Typparametrar

### <a name="state"></a>Status

Den typ av tillstånd som `fn` funktionen körs på, dvs accepterar som första inmatade och returnerade.
### <a name="t"></a>Inte

Typ av `array` element.

## <a name="example"></a>Exempel

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```