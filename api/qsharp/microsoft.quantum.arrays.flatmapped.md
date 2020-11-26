---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Funktionen FlatMapped
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221257"
---
# <a name="flatmapped-function"></a>Funktionen FlatMapped

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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