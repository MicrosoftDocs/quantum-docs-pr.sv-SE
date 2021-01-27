---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842197"
---
# <a name="windows-function"></a>Windows-funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar alla efterföljande under matriser med längd `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Description

Den här funktionen returnerar alla `n - size + 1` undermatriser `size` i ordning, där `n` är längden på `arr` .
De första undermatriserna är `arr[0..size - 1], arr[1..size], arr[2..size + 1]` till och med den sista under matrisen `arr[n - size..n - 1]` .

Om `size <= 0` eller `size > n` , returneras en tom matris.

## <a name="input"></a>Indata

### <a name="size--int"></a>Storlek: [int](xref:microsoft.quantum.lang-ref.int)

Längden på undermatriserna.


### <a name="array--t"></a>matris: ' ' []

En matris med element.



## <a name="output--t"></a>Utdata: ' t [] []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="example"></a>Exempel

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```