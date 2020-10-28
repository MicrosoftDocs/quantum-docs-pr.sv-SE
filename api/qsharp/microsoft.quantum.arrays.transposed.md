---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729979"
---
# <a name="transposed-function"></a>Transponerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Returnerar Transponeringen av en matris som visas som en matris med matriser.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Beskrivning

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