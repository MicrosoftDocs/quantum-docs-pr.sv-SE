---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Uppräknad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221427"
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