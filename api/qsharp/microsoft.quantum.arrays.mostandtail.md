---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Funktionen MostAndTail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220577"
---
# <a name="mostandtail-function"></a>Funktionen MostAndTail

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en tupel av alla utom ett och det sista elementet i matrisen.

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>Indata

### <a name="array--a"></a>matris: "A []

En matris med minst ett element.



## <a name="output--aa"></a>Utdata: ("A []," A)

En tupel av alla utom ett och det sista elementet i matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="a"></a>"A

Typ av mat ris element.