---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exkluderande funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730286"
---
# <a name="excluding-function"></a>Exkluderande funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Returnerar en matris som innehåller elementen i en annan matris, förutom element i en specifik lista med index.

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
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