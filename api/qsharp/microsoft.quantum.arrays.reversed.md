---
uid: Microsoft.Quantum.Arrays.Reversed
title: Omvänd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845460"
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