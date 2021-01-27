---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842880"
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