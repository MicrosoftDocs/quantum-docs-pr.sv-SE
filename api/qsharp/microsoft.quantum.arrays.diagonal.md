---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221546"
---
# <a name="diagonal-function"></a>Diagonal funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en matris med diagonala element i en tvådimensionell matris

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Beskrivning

Om den tvådimensionella matrisen inte har någon kvadratisk form returneras diagonalen över minimivärdet över antalet rader och kolumner.

## <a name="input"></a>Indata

### <a name="matrix--t"></a>matris: ' ' [] []

tvådimensionell matris i rad-till-ordning



## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `matrix` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. transponeras](xref:Microsoft.Quantum.Arrays.Transposed)