---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Funktionen IntegerBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231100"
---
# <a name="integerbits-function"></a>Funktionen IntegerBits

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar alla positioner där bitar av ett heltal anges.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Ett icke-negativt tal.


### <a name="length--int"></a>Längd: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar i den binära expanderingen av `value` .



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris som innehåller alla bit positioner (från 0) som är 1 i den binära expanderingen av `value` alla bitar upp till positionen `length - 1` .  Alla positioner sorteras i matrisen efter position i ökande ordning.