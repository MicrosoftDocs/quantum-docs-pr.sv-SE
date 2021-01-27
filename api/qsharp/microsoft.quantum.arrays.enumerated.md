---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Uppräknad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848130"
---
# <a name="enumerated-function"></a>Uppräknad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris returneras en ny matris som innehåller element från den ursprungliga matrisen tillsammans med indexen för varje element.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Indata

### <a name="array--telement"></a>matris: ' TEleation []

En matris vars element ska räknas upp.



## <a name="output--inttelement"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int), "teleteleering) []

En ny matris som innehåller element i den ursprungliga matrisen tillsammans med deras index.

## <a name="type-parameters"></a>Typparametrar

### <a name="telement"></a>"Teleteleering"

Typ av element i matrisen.

## <a name="example"></a>Exempel

Följande `for` slingor är likvärdiga:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```