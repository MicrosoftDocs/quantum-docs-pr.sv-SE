---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Funktionen IntegerBits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855406"
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

## <a name="example"></a>Exempel

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```