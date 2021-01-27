---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Funktionen HeadAndRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848547"
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