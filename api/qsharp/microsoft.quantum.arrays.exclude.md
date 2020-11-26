---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exkludera funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221359"
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