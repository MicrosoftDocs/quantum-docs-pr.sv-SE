---
uid: Microsoft.Quantum.Arrays.Reversed
title: Omvänd funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220441"
---
# <a name="reversed-function"></a>Omvänd funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapa en matris som innehåller samma element som en inmatad matris men i omvänd ordning.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="array--t"></a>matris: ' ' []

En matris vars element ska kopieras i omvänd ordning.



## <a name="output--t"></a>Utdata: ' t []

En matris som innehåller elementen `array[Length(array) - 1]` .. `array[0]`.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av mat ris element.