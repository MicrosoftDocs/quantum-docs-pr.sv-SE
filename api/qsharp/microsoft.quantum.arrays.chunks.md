---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221614"
---
# <a name="chunks-function"></a>Segment funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Delar upp en matris i flera delar med samma längd.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Indata

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

Längden på varje segment.


### <a name="arr--t"></a>arr: ' t []

Matrisen som ska delas.



## <a name="output--t"></a>Utdata: ' t [] []

En matris som innehåller varje segment i den ursprungliga matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Observera att det sista elementet i utdata kan vara kortare än `nElements` om `Length(arr)` inte är delbar med `nElements` .