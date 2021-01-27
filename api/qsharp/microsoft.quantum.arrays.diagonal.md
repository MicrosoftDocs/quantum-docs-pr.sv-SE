---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842829"
---
# <a name="diagonal-function"></a>Diagonal funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en matris med diagonala element i en tvådimensionell matris

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Description

Om den tvådimensionella matrisen inte har någon kvadratisk form returneras diagonalen över minimivärdet över antalet rader och kolumner.

## <a name="input"></a>Indata

### <a name="matrix--t"></a>matris: ' ' [] []

tvådimensionell matris i rad-till-ordning



## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `matrix` .

## <a name="example"></a>Exempel

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. transponeras](xref:Microsoft.Quantum.Arrays.Transposed)