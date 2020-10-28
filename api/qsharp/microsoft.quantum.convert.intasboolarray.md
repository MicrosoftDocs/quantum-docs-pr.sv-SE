---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Funktionen IntAsBoolArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727537"
---
# <a name="intasboolarray-function"></a>Funktionen IntAsBoolArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paketfilerna [](https://nuget.org/packages/)


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