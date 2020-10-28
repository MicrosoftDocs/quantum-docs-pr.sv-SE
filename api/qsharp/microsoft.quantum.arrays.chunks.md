---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segment funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730414"
---
# <a name="chunks-function"></a>Segment funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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