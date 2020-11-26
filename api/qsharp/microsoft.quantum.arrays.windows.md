---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219897"
---
# <a name="windows-function"></a>Windows-funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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