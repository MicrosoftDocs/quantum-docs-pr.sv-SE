---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Funktionen FlatMapped
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730270"
---
# <a name="flatmapped-function"></a>Funktionen FlatMapped

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Med en matris och en funktion som mappar ett mat ris element till vissa utdata, returnerar de sammansatta utmatnings matriserna för varje mat ris element.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Indata

### <a name="mapper--tinput---toutput"></a>Mapper: ' TInput-> ' TOutput []

En funktion från `'TInput` till `'TOutput[]` som används för att mappa mat ris element.


### <a name="array--tinput"></a>matris: ' TInput []

En matris med element.



## <a name="output--toutput"></a>Utdata: ' TOutput []

En matris `'TOutput[]` som är sammanfogningen av alla matriser som genereras av mappnings funktionen.

## <a name="type-parameters"></a>Typparametrar

### <a name="tinput"></a>'TInput

Typ av `array` element.
### <a name="toutput"></a>'TOutput

`mapper`Funktionen returnerar matriser av den här typen.