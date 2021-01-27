---
uid: Microsoft.Quantum.Arrays.Most
title: De flesta funktioner
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845586"
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