---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Funktionen CumulativeFolded
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730366"
---
# <a name="cumulativefolded-function"></a>Funktionen CumulativeFolded

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Kombinerar mappad och vikning till en enda funktion

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Beskrivning

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