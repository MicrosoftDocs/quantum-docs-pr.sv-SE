---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Funktionen LeftShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219676"
---
# <a name="leftshiftedl-function"></a>Funktionen LeftShiftedL

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Indata

### <a name="value--bigint"></a>värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).


### <a name="amount--int"></a>belopp: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar som ska `value` flyttas till vänster.



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Värdet för `value` , flyttas till vänster med `amount` bitar.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```