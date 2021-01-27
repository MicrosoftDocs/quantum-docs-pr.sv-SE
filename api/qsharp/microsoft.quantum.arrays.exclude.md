---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exkludera funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848666"
---
# <a name="exclude-function"></a>Exkludera funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="remove--int"></a>ta bort: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris med index som anger vilka element som ska uteslutas från utdata.


### <a name="array--t"></a>matris: ' ' []

Matris där värdena i utdatabufferten tas.



## <a name="output--t"></a>Utdata: ' t []

En matris `output` som `output[0]` är det första elementet i `array` vars index inte visas i `remove` , till exempel `output[1]` det andra elementet, och så vidare.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av mat ris element.

## <a name="example"></a>Exempel

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```