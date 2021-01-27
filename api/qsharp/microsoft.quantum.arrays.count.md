---
uid: Microsoft.Quantum.Arrays.Count
title: Funktionen Count
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842841"
---
# <a name="count-function"></a>Funktionen Count

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på en matris och ett predikat som har definierats för elementen i matrisen returnerar antalet element en matris som består av de element som uppfyller predikatet.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Indata

### <a name="predicate--t---bool"></a>predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion från `'T` till boolesk som används för att filtrera element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet element i `array` som uppfyller predikatet.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="example"></a>Exempel

Följande kod visar funktionen "count".
Ett predikat definieras med @"microsoft.quantum.logical.greaterthani" funktionen:

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.