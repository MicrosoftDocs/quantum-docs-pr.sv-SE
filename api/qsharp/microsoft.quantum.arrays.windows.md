---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729934"
---
# <a name="windows-function"></a>Windows-funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Returnerar alla efterföljande under matriser med längd `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Beskrivning

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