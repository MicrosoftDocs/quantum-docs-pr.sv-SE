---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Funktionen RightShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219523"
---
# <a name="rightshiftedl-function"></a>Funktionen RightShiftedL

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Indata

### <a name="value--bigint"></a>värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).


### <a name="amount--int"></a>belopp: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar som ska `value` flyttas till höger.



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Värdet för `value` , flyttas direkt med `amount` bitar.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```