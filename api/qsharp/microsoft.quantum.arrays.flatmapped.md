---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Funktionen FlatMapped
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848645"
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

## <a name="example"></a>Exempel

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```