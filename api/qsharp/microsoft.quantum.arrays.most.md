---
uid: Microsoft.Quantum.Arrays.Most
title: De flesta funktioner
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220611"
---
# <a name="most-function"></a>De flesta funktioner

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en matris som är lika med en indataparameter förutom att det sista mat ris elementet har släppts.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="array--t"></a>matris: ' ' []

En matris vars första till-sista-element är att skapa en matris för utdata.



## <a name="output--t"></a>Utdata: ' t []

En matris som innehåller elementen `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av mat ris element.