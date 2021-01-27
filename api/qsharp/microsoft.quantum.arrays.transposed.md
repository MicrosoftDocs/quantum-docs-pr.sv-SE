---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponerad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850940"
---
# <a name="transposed-function"></a>Transponerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar Transponeringen av en matris som visas som en matris med matriser.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Description

Mata in som en $r \times c $-matris med $r $ rader och $c $ columns.  Matrisen är rad-baserad, d.v.s. kommer att `matrix[i][j]` få åtkomst till elementet på rad $i $ och kolumn $j $.

Den här funktionen returnerar den $c \times r $-matrisen som är transponerad för den angivna matrisen.

## <a name="input"></a>Indata

### <a name="matrix--t"></a>matris: ' ' [] []

Rad-baserad $r \times c $ Matrix



## <a name="output--t"></a>Utdata: ' t [] []

Transponerad $c \times r $ Matrix

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `matrix` .

## <a name="example"></a>Exempel

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```