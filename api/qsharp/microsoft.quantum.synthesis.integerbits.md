---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Funktionen IntegerBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730667"
---
# <a name="integerbits-function"></a>Funktionen IntegerBits

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paketfilerna [](https://nuget.org/packages/)


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