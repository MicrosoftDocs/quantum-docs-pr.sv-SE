---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Funktionen IntAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224351"
---
# <a name="intasboolarray-function"></a>Funktionen IntAsBoolArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genererar en binär representation av ett positivt heltal med hjälp av en liten endian-representation för den returnerade matrisen.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Indata

### <a name="number--int"></a>Number: [int](xref:microsoft.quantum.lang-ref.int)

Ett positivt heltal som ska konverteras till en matris med booleska värden.


### <a name="bits--int"></a>bitar: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar i den binära representationen av `number` .



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

En matris med booleska värden som representerar `number` .

## <a name="remarks"></a>Kommentarer

Inmatade värden `bits` måste vara mellan 0 och 63.
Inmatade värden `number` måste vara mellan 0 och $2 ^ {\texttt{BITS}}-$1.