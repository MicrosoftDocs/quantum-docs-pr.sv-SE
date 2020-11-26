---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Funktionen HeadAndRest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221087"
---
# <a name="headandrest-function"></a>Funktionen HeadAndRest

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en tupel av de första och alla återstående element i matrisen.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Indata

### <a name="array--a"></a>matris: "A []

En matris med minst ett element.



## <a name="output--aa"></a>Utdata: ("A" A [])

En tupel av de första och alla återstående element i matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="a"></a>"A

Typ av mat ris element.