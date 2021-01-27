---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Funktionen IntAsBoolArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833311"
---
# <a name="intasboolarray-function"></a>Funktionen IntAsBoolArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genererar en binär representation av ett icke-negativt heltal med en liten endian-representation för den returnerade matrisen.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Indata

### <a name="number--int"></a>Number: [int](xref:microsoft.quantum.lang-ref.int)

Ett icke-negativt heltal som ska konverteras till en matris med booleska värden.


### <a name="bits--int"></a>bitar: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar i den binära representationen av `number` .



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

En matris med booleska värden som representerar `number` .

## <a name="remarks"></a>Kommentarer

Inmatade värden `bits` måste vara mellan 0 och 63.
Inmatade värden `number` måste vara mellan 0 och $2 ^ {\texttt{BITS}}-$1.