---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Funktionen ColumnAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846262"
---
# <a name="columnat-function"></a>Funktionen ColumnAt

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Extraherar en kolumn från en matris.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Description

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

## <a name="example"></a>Exempel

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. transponeras](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)