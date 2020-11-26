---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Funktionen ColumnAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210111"
---
# <a name="columnat-function"></a>Funktionen ColumnAt

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Extraherar en kolumn från en matris.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Beskrivning

Den här funktionen extraherar en kolumn i en matris i rad-till-ordning.
Extrahera en rad corrsponds till element åtkomst för det första indexet och kräver därför ingen ytterligare behandling.

## <a name="input"></a>Indata

### <a name="column--int"></a>kolumn: [int](xref:microsoft.quantum.lang-ref.int)

Kolumn i matrisen


### <a name="matrix--t"></a>matris: ' ' [] []

tvådimensionell matris i rad-till-ordning



## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `matrix` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. transponeras](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)